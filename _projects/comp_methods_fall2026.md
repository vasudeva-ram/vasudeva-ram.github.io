---
layout: page
title: Computational Methods for Macroeconomics
description: <em>Métodos Computacionales para Macroeconomía</em>
img: assets/course-materials/computational-methods/comp-macro.png
timing: Tuesdays & Wednesdays, 4:00 – 5:30pm
category: fall 2026
importance: 2
giscus_comments: false
---

**Fall 2026 · CIDE Master's in Economics · Solving and Estimating DSGE Models**

## Course Overview

This course provides an overview of solution and estimation techniques for dynamic stochastic general equilibrium (DSGE) models.
We will cover the basics of numerical approximation techniques and introduce latest advances in the field.
By the end, students should be able to construct a model, implement the mathematics required to solve it, estimate it using data, and extend it from the representative household to settings with heterogeneous agents.

The course has four parts.
Part I develops the mathematical foundations on the whiteboard: deterministic and stochastic difference equations, linear rational-expectations systems and the conditions under which they can be solved (Blanchard–Kahn and related), linearization and the state-space representation, higher-order perturbation, a (very brief) overview of projection and global methods, and sequence-space techniques.
Part II turns to model building: a brief treatment of dynamic programming, then the real business cycle and New Keynesian models — derived and solved by hand first, then in Dynare and Helix — and models of permanent shocks and long-run transitions.
Part III focuses on empirical implementation: the state-space form and the Kalman filter, Bayesian inference and posterior simulation, and limited-information approaches such as impulse-response matching.
Part IV introduces incomplete-markets and HANK models, solved using the sequence-space methods.

The course emphasizes practical hands-on experience.
Part I is deliberately kept to the whiteboard — pure mathematics, with analytical problem sets.
From Part II onward, most sessions combine conceptual material with computational exercises, and students are expected to build and solve models themselves rather than just run provided code.
By the end of the course, students should be able to take an unfamiliar published DSGE model, reproduce it, estimate it, and assess its strengths and limitations.
These skills are directly relevant for work in central banks, ministries, and research institutions, and they provide solid preparation for applications to PhD programs.

{% include course_materials.html folder="assets/course-materials/computational-methods" %}
