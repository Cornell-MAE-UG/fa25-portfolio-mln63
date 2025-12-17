---
layout: project
title: Wind Turbine Blade Design
description: Optimization Design Project
technologies: [MatLab, Autodesk Fusion]
image: /assets/images/4272-portfolio-figure0.jpg
---

#### Project Overview
For this project we were asked to design a wind-turbine blade and optimize it for a Weibull-distributed wind environment. As seen in Figure 1, we found that the Weibull probability distribution for wind speed peaked at Uwind=5.2 m/s. When designing our blade, we were aiming to optimize the power output of the wind turbine, keeping in mind the range of wind velocities that were the most probable in a natural environment. Although power output increases with wind speed, it is not practical to optimize a blade to higher flow velocities due to the low probability of their occurrence. The constraints on the blade included geometric constraints limiting the radius, thickness, and chord length and operational/experimental constraints for the maximum stress, torque, and rotation rate to ensure structural integrity and safe operating conditions. We also designed our blade to be easily manufactured for ease of testing, making sure it was able to be 3D printed, avoiding a thin trailing edge, and ensuring there would be no gap between the attachment piece and the blade. 

![Figure 1. Weibull distribution for wind velocity]({{ "4272-portfolio-figure1.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

#### Design Process
In the process of designing our blade, we made several assumptions. We used the Blade Element Momentum theory which requires the assumption that there are no losses from the rotor and that there is no wake rotation. We also assumed that the wind turbine would be operating at the Betz limit, meaning the efficiency of the turbine would be Betz=0.593, and that the turbine would operate at a constant angle of attack maximizing the lift to drag ratio, and with constant lift and drag coefficients. To find these values, we referred to data for flow with low Reynolds numbers over our chosen airfoil, the NACA 4412, and found the angle of attack that resulted in the highest Cl/Cd value. This angle of attack and corresponding lift and drag coefficients were used in the designing of our blade and assumed to remain constant. The bulk of the design process was developing a MatLab script using BEM theory combined with aerodynamics to meet the specifications and optimize the performance. For a specific blade rotation rate, the length of the blade was iterated over and the ideal geometry, overall power output, maximum torque on the blade, and total stress on the blade were determined. The blade rotation rate was then increased and the process was repeated until one of the constraints was no longer met. The geometric distributions from that iteration were then used as our final design. (Figure 2)

The development of the MatLab script and producing the final blade geometry distributions was my main contribution to this project. I looked into what were reasonable assumptions to make and how to balance simplification with accuracy. I determined the best angle of attack and lift and drag coefficients to use in my model and used BEM theory to design a blade for a specific tip speed ratio and ideal operating conditions and altered the geometry to meet all specifications.

![Figure 2. Head on view of final blade design CAD model]({{ "4272-portfolio-figure2.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

#### Testing Summary
Our goal for testing was to determine the rotational speed of the blades that optimize power output and validate the structural stability of our design. We produced power curves (Figure 3) by setting the frequency of the wind tunnel fan and incrementally increasing the torque break voltage and recording the resulting power output until the blades stalled. This was done for various wind speeds ranging from 4.6 m/s to 10.6 m/s with the wind velocity values determined from the fan frequency using a relationship derived in a previous experiment. The power curves were analyzed alongside the Weibull distribution to determine the optimal rotation rate for our blade. Future improvements in our testing procedure include smaller step sizes in torque voltage to improve accuracy and testing more velocities in the Weibull high probability range for a better fit model at lower, more probable velocities. 

![Figure 3. Power curves obtained in testing]({{ "4272-portfolio-figure3.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}