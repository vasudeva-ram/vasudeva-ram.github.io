---
layout: page
title: Log Linearizer
description: SymPy-based code package to log-linearize a system of dynamic equations. 
img: assets/img/LogLin.png
importance: 1
category: other stuff
giscus_comments: false
---

Hate the tedium of log-linearizing your model? 
So do I. 
Feel free to use my SymPy-based code to automatically log-linearize your nonlinear dynamic equations, [LogLinearization](https://github.com/vasudeva-ram/LogLinearization).

Got an entire non-linear model in a DYNARE .mod file?
Log-linearize it in two lines of code.

```python
import LogLinearization as ll

nk, eqns = ll.createModEconomy('SimpleNK.mod') # address of .mod file
for eqn in eqns: 
    display(eqn.loglin())
```
returns

$$\displaystyle \hat{W}_t = \hat{C}_t {\sigma} + \hat{N}_t {\phi}$$



$$\displaystyle - \hat{R}^n_t = \hat{C_t} {\sigma} - \hat{C}_{t+1} {\sigma} - \hat{\Pi}_{t+1}$$



$$\displaystyle \hat{A}_t + \hat{N}_t \left(1 - {\alpha}\right) = \hat{C}_t$$



$$\displaystyle \hat{W}_t = \hat{A}_t - \hat{N}_t {\alpha}$$



$$\displaystyle \hat{R}^r_t = \hat{R}^n_t - \hat{\Pi}_{t+1}$$



$$\displaystyle \hat{R}^n_t = \frac{\bar{\Pi}^{\phi_{\pi}} \hat{\Pi_t} {\phi_{\pi}} + \bar{\varepsilon_m} \hat{\varepsilon}^m_t {\beta}}{\bar{\Pi}^{\phi_{\pi}} + \bar{\varepsilon_m} {\beta}}$$





Just want one quick equation to log-linearize?
That's fast and easy too!

```python
import LogLinearization as ll

euler = '1/R=betta*(C(+1)/C)^(-siggma)/Pi(+1)' # the equation you want to log-linearize
vardict = {'C':'C', 'R':'R', 'Pi':r'\Pi'} # dictionary of endogenous variables, with their TeX representations
paramdict ={'siggma':r'\sigma', 'betta':r'\beta'} # dictionary of parameters, with their TeX representations
ssdict = {'Pi':1}; # dictionary of any simple steady state values

econ = ll.ModEconomy(vardict, paramdict, ssdict)
eqn = ll.Equation(euler, econ)
display(eqn.loglin())
```
returns

$$\displaystyle - \hat{R_t} = \hat{C_t} \sigma - \hat{C}_{t+1} \sigma - \hat{\Pi}_{t+1}$$

Check it out, and please feel free to leave comments.
