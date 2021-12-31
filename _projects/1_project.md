---
layout: page
title: String stable mixed traffic platoon
description: a project with a background image
img: assets/img/12.jpg
importance: 1
category: work
---
### Motivation

In manual driving traffic, the [accordion effect](https://en.wikipedia.org/wiki/Accordion_effect), i.e., the velocity fluctuation propagates from the preceding vehicle to the following vehicle, is one of the major causes of traffic flow disruption, driving efficiency, or even collision. In contrast, string stability has been a popular concept for the autonomous driving platoon to avoid the accordion effect. One step further, considering a more practical scenario where the traffic is mixed with autonomous cars and manual cars, can we design a guideline for the autonomous driving algorithm and the traffic arrangement such that velocity fluctuations are not propagated, and the platoon is collision-free?

### Methodologies and results

* Mixed traffic string stability has been defined (Definifition 1 in [1]) such that the velocity fluctation is acceptatble and the rear-end collision should be avoid. 

* The theorem (Theorem 1 in [1]) has been developed and proved that the mixed traffic string stability can be achieved if 

$$
\begin{aligned}
&\|G^{\Lambda}_{i,1}(s)\|_{H_\infty} \leq \|G^{*}_{h_a}(s)\|_{H_\infty},~\forall \ i >1,  \\
&\|g^{\Lambda}_{i,1}(t)\|_1 \leq \|g^{*}_{h_a}(t)\|_1,~\forall \ i > 1,\\
&\|v_1(t)-v_1(0)\|_\infty
\leq\min\left(\frac{h_{\Phi(i)}v_1(0)}{\|g^{'}_{\Phi(i)}(t)\|_1\|g^{*}_{h_a}(t)\|_1},\frac{h_{\Phi(2)}v_1(0)}{\|g^{'}_{\Phi(2)}(t)\|_1}\right), \forall i>2,
\end{aligned}
$$

>>Intuitively, the above reuqirements can be achieved by suitable design of the autonomous driving systems, the arrangement ofthe mixed traffic sequence. More details on derivations and proof can be found in [1] 

* It has been rigorous proved that the mixed taffic string stability can be guaranteedby adjusting the time headway of autonomous cars or inserting anadditional autonomous cars (Theorem 2 in [1])

### Application

* Given a mixed traffic platoon Theorem 1 can be used to check if it is string stable
* String stable controller design guidance can be provided 

