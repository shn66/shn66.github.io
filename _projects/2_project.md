---
layout: page
title: Multi-modal Collision Avoidance
description: Designing efficient MPC schemes for avoiding collisions against obstacles with dynamic, multi-modal uncertainties
img: assets/img/proj2.gif
importance: 2
category: UC Berkeley
---


On this page, we highlight our work on efficient, non-conservative collision avoidance in the presence of multi-modal predictions of traffic vehicles, for autonomous driving.


Our main theoretical contributions include:

 <i>(1)</i> <b>Robust, Stochastic and Distributionally Robust MPC formulations that optimize over a novel feedback policy class designed to exploit additional structure in the multi-modal predictions, and that is amenable to convex programming </b>. 
  <div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/no_pol_new.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/pol_new.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   On the left, the ego vehicle plans using open-loop predictions. On the right, the ego vehicle plans using multi-modal policies
</div>

 The use of feedback policies for prediction is motivated by the need for reduced conservatism in handling multi-modal predictions of the surrounding vehicles, especially prevalent in urban driving scenarios. 



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include googleDrivePlayer.html id="1IKW7o9npx8SbyBD9x_NArcBp3svfztAD/preview" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include googleDrivePlayer.html id="1aqGxcNWGwr-ICOIOesLP1zobcy54yxXB/preview" %}
    </div>
</div>
<div class="caption">
    Multi-modal collision avoidance for an unprotected left turn in CARLA. 
</div>


 <i>(2)</i> <b>Convexified, optimization-based collision avoidance between convex sets in the presence of uncertainty</b>. 
 
<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/of.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/obca.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   On the left, typical vehicle geometry representations. On the right, an illustration of separating hyperplanes found by the MPC algorithm
</div>

Collision avoidance constraints in the presence of uncertainty, are typically imposed by conservatively approximating the vehicle geometry as a (i) point, (ii) affine space, (iii) spheres or (iv) ellipsoids, instead of using polytopes to avoid non-smooth constraints. We use the dual perspective of collision avoidance to find separating hyperplanes between vehicles expressed as polytopes, while simulatenously accounting for the uncertainty in their locations.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_sim.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   We compare the separating hyperplane optimization approach, with the conventional, ellipsoidal approximation approach. We see that the former produces tighter turns even in the presence of uncertainty.
</div>


For more details, please see our papers from <a href="https://arxiv.org/pdf/2109.09792.pdf">ITSC'22</a> and <a href="https://arxiv.org/pdf/2208.03529.pdf">CDC'22</a>.


# Upcoming: 
In addition to using multi-modal policies, we derive a convex formulation for simulataneous risk allocation and optimization of policies for multi-modal obstacle avoidance constraints. The figure below underscores the importance of this contribution. For $$x$$ given by a Gaussian mixture (where $$x$$ could denote the distance between vehicles), the figure depicts two formulations for shaping its multi-modal distribution via the means $$\mu$$ to satisfy $$\mathbb{P}(x>0)\geq p^\star$$.
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/mm_fixed_vs_risk.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
The resulting distributions are shown on the right for the uniform risk and variable risk allocation formulations at the top and bottom respectively. The latter allows satisfaction of the chance constraint without agressive shaping of the distribution, by exploiting the difference in probabilities of the modes. Consequently, this improves the feasibility of MPC optimization problems by allocating less risk to unlikely modes, without compromising on safety! 
This approach was recently developed and implemented on a full-scale vehicle in collaboration with <a href="https://www.google.com/url?q=https%3A%2F%2Fwww.linkedin.com%2Fin%2Fhotae-lee%2F&sa=D&sntz=1&usg=AOvVaw12b_X0XdZSd5_e4wYyrdx5">Hotae Lee</a> and <a href="https://www.linkedin.com/in/ejoa/">Eunhyek Joa</a>:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include googleDrivePlayer.html id="1EQJmVHb3AExu1rs3Mw4PRdML_TmWqSpW/preview" %}
    </div>
</div>
<div class="caption">
    Autonomous lane change at the Richmond Field Station in the presence of two virtual vehicles, with bi-modal predictions. The experimental setup is largely based on <a href="https://arxiv.org/pdf/2304.08576.pdf">Joa*, Lee* et al., IV'23</a>.
</div>

The technical details will be available soon. Stay tuned!





