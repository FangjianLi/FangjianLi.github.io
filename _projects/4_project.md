---
layout: page
title: HRI in vehicle team under cyber attack
description: a human-robot interaction (HRI) framework to help vehicle team under cyber attacks
img: assets/img/hri_cover.jpg
importance: 1
category: 'Research: help from the human'
---

### Motivation

Although the autonomous vehicle team has achieved success in recent years, human operator supervision is still vital in dealing with uncertainties and emergencies. For the autonomous vehicle driving team, the cyber attack is one of the most challenging threats. In this project, a human-robot interaction (HRI) framework has been proposed to improve the survivability of the vehicle team under cyber attacks. Specifically, both vehicle-to-vehicle (V2V) and vehicle-to-cloud (V2C) cyber attacks. 

### Methodologies

* The HRI framework is composed of three systems, i.e., anomaly reporting system (ARS),  trust-based information management system  (TIMS), and graphical user interface (GUI). The block diagram is shown in the following figure. 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/HRI_framework.jpg" title="HRI framework" class="img-fluid rounded z-depth-1" %}
</div>

* The ARS can be used to detect the abnormality of the neighbor vehicles based on the **residual generation and analysis** technique. The report will be sent to the cloud. 

* Due to the V2V cyber attacks, the reports sent by ARS can be compromised. Correspondingly, TIMS (a **Bayesian inference-based** information processor with a **trustworthiness** regulator) is used to process the compromised reports and identify the abnormal vehicles. 

* The abnormality probability of each vehicle is shown in the **GUI**. The human operator can then teleoperate it. Moreover, human opinion can also feed into the TIMS to refresh the system. 

* A very preliminary version has been pubslished in our paper [2]. The full verison is under review [3].

### Results

* The simulation environment is built with **SIMULINK**. The 3D world is built with **MATLAB 3D toolbox**. The GUI is built with **MATLAB GUIDE**. 

* Based on the human subject test, it has been shown that our proposed HRI framework can greatly improve human performance and reduce human workload. 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/HRI_setup.jpg" title="HRI setup" class="img-fluid rounded z-depth-1" %}
</div>

> **[[2] Li, Fangjian, et al. Trust-based control and scheduling for UGV platoon under cyber attacks. No. 2019-01-1077. SAE Technical Paper, 2019.](https://www.sae.org/publications/technical-papers/content/2019-01-1077/)** <br>
> **[3] Li, Fangjian, et al. Unmanned Ground Vehicle Platooning under CyberAttacks: A Human-Robot Interaction Framework. 
under review in IEEE Transactions on Intelligent Transportation Systems**
