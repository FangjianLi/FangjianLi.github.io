---
layout: page
title: Resilient CACC under cyber attacks
description: a resilient vehicle autonomous longitudinal controller under cyber attacks
img: assets/img/resilient_cover.jpg
importance: 2
category: 'Research: help from the human'
---

### Motivations
The vehicle-to-vehicle (V2V) communication can improve the autonomous vehicle driving efficiencies and safety. However, the V2V cyber attacks bring about new threats and hinders its wide applications in the real world. In this project, a resilient controller is designed for the autonomous longitudinal controller in resisting the V2V cyber attacks. 

### Methodologies 

* The resilient controller is designed based on the unknown input observer (UIO). The block diagram is shown below. More details can be found in our paper [2].

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/OBRC_structure.jpg" title="OBRC structure" class="img-fluid rounded z-depth-1" %}
</div>

* It has been proved that this controller is asmptotically stable, string stable (without cyber attacks). (our paper under review [3])

>>It is also rigorously calculated the maximum V2V cyber attack value, i.e.,  $$\|\zeta_i(t)\|_\infty$$, that the proposed resilient controller can resist in order to fulfill the safety. (our paper under review [3])

$$
\begin{equation}
    \|\zeta_i(t)\|_\infty\!<\!\frac{h^*_iv_i(0)\!-\!\|g_{r,i}(t)\|_1\|v_{i-1}(t)\!-\!v_{i-1}(0)\|_\infty-\epsilon}{\|g_{e,i}(t)\|_1},
\end{equation}
$$

* The safety conditions for the vehicle team under cyber attacks have also been calculated (our paper under review [3]).

### Results

* The system models of the oberver-based resisilent controller (OBRC) and benchmark controller have been built in **SIMULINK**. The performance comparion are shown as follows. (more details can be found in [2]). 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/OBRC_performance.jpg" title="OBRC performance" class="img-fluid rounded z-depth-1" %}
</div>

> **[2] Li, Fangjian, et al. Trust-based control and scheduling for UGV platoon under cyber attacks. No. 2019-01-1077. SAE Technical Paper, 2019.** <br>
> **[3] Li, Fangjian, et al. Unmanned Ground Vehicle Platooning under CyberAttacks: A Human-Robot Interaction Framework. 
under review in IEEE Transactions on Intelligent Transportation Systems**
