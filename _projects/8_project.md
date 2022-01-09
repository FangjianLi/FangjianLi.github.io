---
layout: page
title: interactive safety cirtic networks 
description: a safety critic network considering the interactions between neighbor cars
img: assets/img/interactive_safety_critic_cover.jpg
importance: 6
category: 'Research: learn from the human'
---

**This is my on-going research. The technical details and codes will be updated soon.**

### Motivation

Safety is of great importance for reinforcement learning in robotics and autonomous driving. Correspondingly, lots of techniques have been used to incorporate the safety concept in the RL algorithms, such as the Hamilton-Jacobi-Isaacs (HJI) reachability approach and control barrier function (CBF) analysis. In this project, a novel safety critic that evaluates the safety level of the current driving state is proposed. Moreover, the safe control input that can maximize the safety level is also generated. Comparing to the state-of-arts, the proposed work rigorously considers the interactions with the neighbor cars but does not require the preknowledge of the system dynamic equations. 

### Human data sampling


In this project, real human data will be collected from the built driving simulator. The human participants (drivers) are required to behave irresponsible or even aggressive towards the car controlled by the learning algorithm. Correspondingly, the driving simulator is built/written such that it can have the following features.

* The driving simulator has three kinds of cars, i.e., the autonomous car controlled by the user-defined learning algorithm, the manually driven car controlled by the human participant, and the neighbor cars modeled by the driver models. 
* The collected data are in the form of (state, action) in the MDP model. As a result, the data can be directly used for training purposes. 
* Modular design. In the no-rendering mode, the driving simulator should be lightweight in order to speed up the sampling process in RL training. 
* The Carla is integrated with this driving simulator, such that the animation is rendered by the Unreal engine. 
* It can accommodate two kinds of human input. One is the low-level control input from the steering wheel and pedals. The other option is the decision-making command, e.g., changing to the left/right lane. 

The codes will be available in my Github repository soon. Here are some video captures (the yellow car is controlled by a user-defined learning algorithm, the green car is controlled by the human, and blue cars are modeled by the driver models):


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
    

