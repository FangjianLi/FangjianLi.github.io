---
layout: page
title: HRI in vehicle team under cyber attack
description: a human-robot interaction framework to help vehicle team under cyber attacks
img: assets/img/platoon_project.jpg
importance: 4
category: work
---

### Motivation

Although the autonomous vehicle team achieved success in recent years, human operator supervision is still vital in dealing with uncertainties and emergencies. For the autonomous vehicle driving team, the cyber attack is one of the most challenging threat to deal with. In this project, a human-robot interaction (HRI) framework has been proposed to improve the surviability of teh vehicle team under cyber attacks. Be more specifically, bothe vehicle-to-vehicle (V2V) and vehicle-to-cloud (V2C) cyber attack 

### Methodologies

* The HRI framwork is composed of three systems, i.e., anomaly  reporting  system (ARS),  trust-based  information  management  system  (TIMS), and graphical user interface (GUI). The block diagram is shown in the following figure. 

<div class="row justify-content-sm-center">
{% include figure.html path="assets/img/HRI_framework.jpg" title="HRI framework" class="img-fluid rounded z-depth-1" % max-width="600px"}
</div>

* The ARS can be used to detect the abnormality of the neigbor vehicles based on the residual generation and anslysis technique. The report will be sent to the cloud. 

* Due to the V2V cyber attacks, the reports sent by ARS can be compromised. Correspondingly, TIMS (a bayesian inference based information processor with trustworthiness regulator) are used to process these reports and identify the abnormal vehicles. 

* The abnormality probability of each vehicle is shwon in the GUI. The human operator can then teleoperate it. Moroever, the human opinion can also feed into the TIMS to refresh the system. 

* The very preliminary version has been pubslished in our paper [3]. The full verison is under review [4].

### Results

* The simulation environment is built based on **SIMULINK**. The 3D world is built on **MATLAB 3D toolbox**. The GUI is built on **MATLAB GUIDE**. 

* Based on the human subject test, it has been shown that our proposed HRI framework can greatly improve the human performance and reduce the human workload. 

{% include figure.html path="assets/img/HRI_setup.jpg" title="HRI setup" class="img-fluid rounded z-depth-1" %}


