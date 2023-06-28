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


## Full-scale Vehicle Experiments COMING SOON!





