---
layout: page
title: String stable mixed traffic platoon
description: an efficient and safe vehicle team
img: assets/img/platoon_cover.jpg
importance: 2
category: 'Research: accomodation for the human'
---
### Motivation

Ideally, a well-designed autonomous driving platoon (team of cars) is string stable and hence can avoid the notorious [accordion effect](https://en.wikipedia.org/wiki/Accordion_effect). However, autonomous driving cars still need to share the road with manual driving cars in the near future, which forms mixed traffic. In this project, we designed a rigorous guideline, i.e., mixed-traffic string stability, for the autonomous driving controller and the traffic arrangement to regulate the efficiency and safety of the mixed traffic.

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/traffic_jam_effect.gif" title="accordion effect" class="img-fluid rounded z-depth-1" %}
</div>

### Methodologies and results

* Mixed traffic string stability has been defined (Definition <span style="color:purple">1</span> in [<span style="color:purple">1</span>]) such that the velocity fluctuation is acceptable and the rear-end collision is avoided. 

* A theorem (Theorem 1 in [1]) has been developed and proved that the mixed traffic string stability can be achieved if 

$$
\begin{aligned}
&\|G^{\Lambda}_{i,1}(s)\|_{H_\infty} \leq \|G^{*}_{h_a}(s)\|_{H_\infty},~\forall \ i >1,  \\
&\|g^{\Lambda}_{i,1}(t)\|_1 \leq \|g^{*}_{h_a}(t)\|_1,~\forall \ i > 1,\\
&\|v_1(t)-v_1(0)\|_\infty
\leq\min\left(\frac{h_{\Phi(i)}v_1(0)}{\|g^{'}_{\Phi(i)}(t)\|_1\|g^{*}_{h_a}(t)\|_1},\frac{h_{\Phi(2)}v_1(0)}{\|g^{'}_{\Phi(2)}(t)\|_1}\right), \forall i>2,
\end{aligned}
$$

>>Intuitively, the above conditions can be achieved by the suitable design of autonomous driving systems and the arrangement of the mixed traffic sequence. More details on derivations and proofs can be found in our paper [1] 

* It has been rigorous proved that the mixed traffic string stability can be guaranteed by adjusting the time headway of autonomous cars or inserting additional autonomous cars (Theorem 2 in [1])

### Application

* Given a mixed traffic platoon Theorem 1 can be used to check if it is string stable
* String stable controller design guidance can be provided 

>**[[1] Li, Fangjian, and Yue Wang. "Cooperative adaptive cruise control for string stable mixed traffic: Benchmark and human-centered design." IEEE Transactions on Intelligent Transportation Systems 18.12 (2017): 3473-3485](https://ieeexplore.ieee.org/abstract/document/8094925).**
