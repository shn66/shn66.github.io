---
layout: page
title: Fast Mixed-integer MPC
description: Predicting parametric optimality certificates using supervised learning for fast MPC
img: assets/img/proj3.png
importance: 3
category: UC Berkeley
---

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

We propose a supervised learning framework for
computing solutions of multi-parametric Mixed Integer Linear
Programs (MILPs) that arise in Model Predictive Control.
Our approach also quantifies sub-optimality for the computed
solutions. Inspired by Branch-and-Bound techniques, the key
idea is to train a Neural Network/Random Forest, which for
a given parameter, predicts a strategy consisting of (1) a set
of Linear Programs (LPs) such that their feasible sets form a
partition of the feasible set of the MILP and (2) a candidate
integer solution. For control computation and sub-optimality
quantification, we solve a set of LPs online in parallel. We
demonstrate our approach for a motion planning example and
compare against various commercial and open-source mixedinteger programming solvers.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/solve_times_N20.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

For more details, please see our LCSS'23 <a href="https://ieeexplore.ieee.org/document/10149475">paper</a>.

## Stay tuned for an end-to-end extension and hardware experiments!
