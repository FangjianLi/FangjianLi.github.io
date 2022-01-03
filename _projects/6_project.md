---
layout: page
title: safe adversarial inverse reinforcement learning (S-AIRL）
description: a safety-aware IRL algorithm with an application of highway driving scenario
img: assets/img/sairl_cover.jpg
importance: 5
category: work
---


### Motivation

Reinforcement learning (RL) has achieved lots of sucess in training the policy control policy. One step further, given the expert demonstrations, the inverse reinforcemeant learning (IRL) can avoid the necessity of handtunning the reward function. However, similar to other policy learning lagorithms, IRL suffers from the safety concern. What's more, IRL is even more vunlerable to the unsafe issue, as it can only infer the importance of the safety from dritribution matching. In this project, the safety-aware inverse reinforcement learning has been developed to improve the safety of the algorithm. 

### Methodologies 
* The overall structure is shown in the following picture. More details can be found in our paper [4].

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_structure.jpg" title="sairl_structure" class="img-fluid rounded z-depth-1" %}
</div>

* First of all, to quantify the safety level of state action pairs $$(s,a)$$, a safety critic network is trained based on the guidance of the control barrier function (CBF). The model-based knowledge, i.e., CBF, is incoporated into the model-free method, i.e., safety critic network, can avoid the necessity of training another guiding policy and can also ender  a  more sufficient exploration. As a result, the trained CBF-based safety critic $$Q^{\textrm{CBF}}_{\textrm{safe}}(s,a)$$ can qunatify the safety probabiliy of the state-action pairs in the future. 

* Seond, to inject the safety-awareness, the trained safety cirtic  $$Q^{\textrm{CBF}}_{\textrm{safe}}(s,a)$$ is intergrated with the discriminator such that the safety feature will be considered in the distribution discrimination process (between trajectories from expert and learned policy). 

* Third, to make sure safety plays an important role, a regulator is added to the algorithm to punish the revovered reward from assigning high rewards to the risky state action pairs. 


### Results

* The training algorithm is written with Tensorflow. We test our algorithm in the highway driving scenario in the simulator highway-env. 

* Albation test is also conducted without the regulator, i.e., SAIRL/Reg.

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_setup.jpg" title="sairl_setup" class="img-fluid rounded z-depth-1" %}
</div>

* The scripts run in the high-performance computing (HPC) resources Palmetto cluster at Clemson University. To facilitate the HPC, parallel samplers are written with ray to greatly improve the sampling speed. The codes of SAIRL and PPO with parallel sampling feature can be found in my Github repository
* Comparing to the benchmark IRL algorithm AIRL, with the same level of imitation learning performance, the collision rate has been reduced by 30%. 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_performance.jpg" title="sairl performance" class="img-fluid rounded z-depth-1" %}
</div>

* The driving comparisons are shown here. 

{% include figure.html path="assets/img/AIRL_DRIVE.gif" title="AIRL" class="img-fluid rounded z-depth-1" %}
{% include figure.html path="assets/img/SAIRL_REG_DRIVE.gif" title="SAIRL" class="img-fluid rounded z-depth-1" %}
{% include figure.html path="assets/img/SAIRL_DRIVE.gif" title="SAIRL" class="img-fluid rounded z-depth-1" %}
