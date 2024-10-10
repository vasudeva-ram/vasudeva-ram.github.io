---
layout: page
title: Julia SSJ
description: Solving HANK models using the Sequence Space Jacobian method in Julia
img: assets/img/jacobian.svg
importance: 2
category: fun
giscus_comments: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/IRFs.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/jacobian.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fakenews.svg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Output for a basic Krussell-Smith Model: IRFs, the Jacobian, and the Fake News Matrix.
</div>

The purpose of this project is to create a series of teaching materials for solving HANK models in Julia using the Sequence Space Jacobian method ([Auclert, Bardoczy, Rognlie and Straub](https://web.stanford.edu/~aauclert/sequence_space_jacobian.pdf)).
The easy part was writing the code in Julia to solve HANK models using the SSJ method.
Writing the learning material, on the other hand, is taking forever.
Too many projects competing for my time, sadly.

To be clear, I think the paper is very well written and easy to follow.
Plus, the Shade-Econ team has done very well to put out Python-based training materials on using their [package](https://github.com/shade-econ/sequence-jacobian).
I intend my materials to be for students who are relatively new to the literature and are not fully familiar with the prerequisites for using the SSJ method.
For example, the SSJ method assumes the availability of a transition matrix $$\Lambda$$ that represents the law of motion for the wealth ditribution of the household sector. 
But where does this come from? 
How does one _actually_ implement the Young (2010) lottery method to obtain this matrix?
Or how does one implement the Carroll (2006) endogenous gridpoint method to obtain the policy functions?
These are the questions that I find students ask most often, and which I hope to answer in detail in these materials.

When I finally get to it, that is.

In the meantime, the link to the code in Julia itself is available [here](https://github.com/vasudeva-ram/Julia-SSJ).


