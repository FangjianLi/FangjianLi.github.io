---
layout: page
title: interactive safety cirtic networks 
description: a safety critic network considering the interactions between neighbor cars
img: assets/img/sairl_cover.jpg
importance: 6
category: 'Research: learn from the human'
---

**This is my on-going research. The technical details and codes will be updated soon.**

### Motivation

Safety is of great importance for the reinforcement learning in the robotics and autonomous driving. Correspondingly, lots of techniques has been used to incorporate safety concept in the RL algorithms, such as the Hamilton-Jacobi-Isaacs (HJI) reachability approach and control barrier function (CBF) analysis. In this project, a novel safety critic that can evaluate the safety level of current driving state is proposed. Morover, the safe control input that can maximzie the safety level is also generated. Comparing to the state-of-arts, the proposed work rigorously considers the interactions with the neghbor cars but do not requrie the preknowledge of the system dynamic equations. 

### Human data sampling

In this project, the real human data will be collected from the built driving simulator. The human participants (drivers) are required to behavior inresponsible or even agressive towards to the car controlled by the learning algoirthm. Corresponding, the dirving simulator is built/written such that it can have the following features

* The driving simulator have three kinds of cars, i.e., the autonomous car controlled by the user-defined learning algorithm, the manual driven car controlled by the human participant, and the neigbor cars modeled by the driver models. 
* The collected data are in the form of (state, action) in MDP model. As a result, the data can be directly used for training purpose. 
* Modular design. In the no-rendering mode, the driving simulator should be light-weight in order to speed up the sampling process in RL training. 
* The Carla is integrated with this driving simulator, such that the animation is rendered by the Unreal enginer from Carla. 
* It can accomodate two kinds of human input. One is the low-level control input from steering wheel and pedals. The other option is the high level decision making command, e.g., change to the left lane/right lane. 

The codes will be availabe in my Github repository soon. Here are some video captures (the yellow car is controlled by a user-defined learning algorithm, green car is controlled by the humam, and blue car is modeled by the driver models):


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/continuous_action_input.gif" title="Continuous action input" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/decision_making_action.gif" title="Decision making input" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">

<div class="row justify-content-sm-center">
    {% include figure.html path="assets/img/preliminary_demo.gif" title="Preliminary demos" class="img-fluid rounded z-depth-1" %}
</div>
    

