---
layout: page
title: Human centered CACC design
description: a comfortable longitudinal vehicle controller
img: assets/img/cacc_project.jpg
importance: 2
category: work
---

### Motivation

With the development of the autonomous driving systems, the role of the human has been transited from driver to the passenager. In this project, we want to design a autonomous longitudinal vehicle controller to improve human comfort.  

### Methodologies 

* The jerk (derivatives of longituinal acceleration) is used to quantify the **physical comfort** of the driver and driving smoothness. 
* The psychophysical car-following model (i.e., AP model in [external 1]) is used to quantify **psychological comfort** of the driver. In the psychophysical car-following model, different driving regimes are separated based on the human driver’s perceptual thresholds (i.e. SDX, OPDV, SDV and BX).For example, BX represents the minimum following threshold for the human driver. Here, we focus more on the unconscious regime (white area), where a human driver cannot perceive any relative motion with the preceding car despite generating small acceleration/deceleration unconsciously. If the driving states of the vehicle can within the unconscious regime, human’s nerve is less stimulated during the normal operating mode and more relaxed.
>> In this way, human workload in monitoring the CACC car operation can also be reduced, since human’s nerve is less stimulated during the normal operating mode.
* An **MPC-like** optimal controller is designed to improve both physical comfort and psychological comfort. The optimal control problem is formulated as follows: 
$$
J_i=c_1 \sum^{T_b} \| d_i \|_2  + c_2 \sum^{T_b}\|u_i\|_2 + c_3 \sum^{T_b} \|jerk_i \|_2 + c_4 \sum^{T_b} \| z_i \|.
\label{cost_function}
$$<br>

$$\qquad$$ with constraints:<br>

$$
\begin{aligned}
&\|\lambda_i(t)-\lambda_{i}(0)\|_p \leq \|\lambda_{i-1}(t)-\lambda_{i-1}(0)\|_p\\
&\|\lambda_{i+j}(t)-\lambda_{i+j}(0)\|_2 \leq \|G^*_{h_a}(s)\|_\infty\|\lambda_1(t)-\lambda_1(0)\|_2\\
&\|\lambda_{i+j}(t)-\lambda_{i+j}(0)\|_\infty \leq \|g^*_{h_a}(t)\|_1\|\lambda_1(t)-\lambda_{1}(0)\|_\infty\\
&d_{i+j}(t)\geq \max\{TTC\left(v_{i+j}(t)-v_{i+j-1}(t)\right),d_{\min}\}
\end{aligned}
$$<br>

The details can be found in our paper [1].<br>

### Results

* The simulation has been done with **MATLAB**+**SIMULINK**+**CARSIM**.
* Comparing to the benchmark controller design, the human driver comfort have been improved largely. 


### Application
* A autonomous vehicle longitudinal controller is designed to improve the driver comfort. 
* This controller can also help human performance in monitoring the operation of the autonomous driving system (longitudinal). 

>**[1] Li, Fangjian, and Yue Wang. “Cooperative adaptive cruise control for string stable mixed traffic: Benchmark and human-centered design.” IEEE Transactions on Intelligent Transportation Systems 18.12 (2017): 3473-3485.**
