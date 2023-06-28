---
layout: page
title: Data-driven Nonlinear MPC
description: Using trajectory traces of nonlinear systems for designing robust MPC with guarantees 
img: assets/img/proj1.gif
importance: 1
category: UC Berkeley
---

In this project, we develop data-driven MPC for constrained optimal control of nonlinear systems with a specific emphasis on <b style='color:#8FAADC;'>safety</b>, <b style='color:#00B050;'>performance</b> and <b>computational efficiency</b>.

<div class="row">
    <div class="col-sm-1 mt-3 mt-sm-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/nMPC.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-1 mt-3 mt-sm-0">
    </div>
</div>



Towards <b style='color:#8FAADC;'>safety</b>, we propose a non-parametric technique to construct prediction models for nonlinear systems with Lipschitz/Lur'e unmodelled dynamics. We use set membership to approximate the graph (in the set-theoretic sense) of the unknown function via <b>semidefinite programming</b> using incremental quadratic constraints. 

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-sm-0">
        {% include figure.html path="assets/img/lip.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Set membership for approximating the graph of the unmodelled dynamics
</div>

This technique has been used for (I) <a href="https://arxiv.org/pdf/1910.03719.pdf">computation of tractable bounds for unmodelled dynamics</a>, (II) <a href="https://arxiv.org/pdf/1910.03719.pdf">computation of positive invariant sets</a>  and (III) <a href="https://arxiv.org/pdf/1910.04378.pdf"> adaptive constraint tightening for adaptive MPC</a>


Towards <b style='color:#00B050;'>performance</b>,  we propose a <b>convex value function</b> representation for flat nonlinear systems defined over <b>convex safe sets</b> in the space of output sequences. The value function and the safe set can be constructed from historical system trajectory data. We show that the output sequences in this safe set map to state and inputs within constraints. Moreover, we provide iterative performance improvement guarantees for the closed-loop system trajectories by using the value function approximation in our MPC design: <a href="https://arxiv.org/pdf/2004.05173.pdf">Output-lifted Learning Model Predictive Control (OLMPC)</a>. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/olmpc1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/olmpc2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   The output sequences (termed "<i>lifted-outputs</i>") map to safe state and inputs of the nonlinear system. The historical lifted-output data are used to contruct <i> convex value functions</i> and <i>safe sets</i> for the MPC design.
</div>

The two ideas presented above culminated in <a href="https://arxiv.org/pdf/2303.12127.pdf">Robust Output-lifted LMPC (ROLMPC)</a>, which was recently implemented on the Berkeley Autonomous Racing Car (BARC) in collaboration with <a href="https://www.google.com/url?q=https%3A%2F%2Fwww.linkedin.com%2Fin%2Fedward-zhu%2F&sa=D&sntz=1&usg=AOvVaw0Ne7U1y50EBnLx17dM7UMP">Edward Zhu</a>:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include googleDrivePlayer.html id="1OK1RtkVIzeBfjG4hDS3yHzaEufGW-wEA/preview" %}
    </div>
</div>
<div class="caption">
    ROLMPC demonstrated on the BARC. First, the gap between the nominal and true models are quantified to compute tightened constraints. Then, the BARC iteratively constructs the safe set and value function to improve lap times. 
</div>




