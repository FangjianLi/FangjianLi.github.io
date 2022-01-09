---
layout: page
title: safe adversarial inverse reinforcement learning (S-AIRL）
description: a safety-aware IRL algorithm with an application of highway driving scenario
img: assets/img/sairl_cover.jpg
importance: 5
category: 'Research: learn from the human'
---


### Motivation

Reinforcement learning (RL) has achieved lots of success in training the optimal control policies. One step further, given the expert demonstrations, inverse reinforcement learning (IRL) can avoid the necessity of hand-tuning the reward function. However, similar to other policy learning algorithms, IRL suffers from safety concerns. What's more, IRL is even more vulnerable to unsafety, as it can only infer the importance of safety from the distribution matching. In this project, a safety-aware inverse reinforcement learning algorithm has been developed to improve the safety of the algorithm. 

### Methodologies 
* The overall structure is shown in the following picture. More details can be found in our paper [4].

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_structure.jpg" title="sairl_structure" class="img-fluid rounded z-depth-1" %}
</div>

* First of all, to quantify the safety level of state-action pairs $$(s, a)$$, a safety critic network is trained based on the guidance of the control barrier function (CBF) technique. The model-based knowledge (CBF) incorporated into the model-free method (safety critic network) can avoid the necessity of training another guiding policy and render a more sufficient exploration. As a result, the trained CBF-based safety critic $$Q^{\textrm{CBF}}_{\textrm{safe}}(s,a)$$ can quantify the safety probability of the state-action pairs in the future. 

* Second, to inject the safety awareness, the trained safety critic $$Q^{\textrm{CBF}}_{\textrm{safe}}(s, a)$$ is integrated with the discriminator such that the safety feature will be considered in the distribution discrimination process (between trajectories from expert and learned policy). 

* Third, to make sure safety plays an important role, a regulator is added to the algorithm to prevent the recovered reward from assigning high rewards to the risky state-action pairs. 


### Results

* The training algorithm is written with **Tensorflow**. We test our algorithm in the highway driving scenario with the simulator [highway-env](https://github.com/eleurent/highway-env), where the environmental cars are modeled by IDM and MOBIL.

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_setup.jpg" title="sairl_setup" class="img-fluid rounded z-depth-1" %}
</div>

* Albation test is also conducted without the regulator, i.e., SAIRL/Reg.

* The scripts run in the **high-performance computing (HPC)** resources [Palmetto cluster](https://citi.sites.clemson.edu/infrastructure/) at Clemson University. To facilitate the HPC process, parallel samplers are written with **Ray** to improve the sampling speed greatly. The codes of AIRL and PPO with parallel sampling feature can be found in my Github [repository](https://github.com/FangjianLi/PPO-and-AIRL-with-parallel-sampling)

* Comparing to the benchmark IRL algorithm AIRL, the collision rate with S-AIRL has been reduced by 30%. 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/sairl_performance.jpg" title="sairl performance" class="img-fluid rounded z-depth-1" %}
</div>

* The driving comparisons (under four parallel driving preceding cars) are shown here. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/AIRL_DRIVE.gif" title="AIRL" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SAIRL_REG_DRIVE.gif" title="SAIRL/REG" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SAIRL_DRIVE.gif" title="SAIRL" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

> **[[4] Li, Fangjian, Wagner, John R, and Wang, Yue, "Safety-aware Adversarial Inverse Reinforcement Learning (S-AIRL) for Highway Autonomous Driving", accepted in ASME Journal of Autonomous Vehicles and Systems, 2022](https://asmedigitalcollection.asme.org/autonomousvehicles/article/doi/10.1115/1.4053427/1131059/Safety-aware-Adversarial-Inverse-Reinforcement).**
