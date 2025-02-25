# My Longtime Friend Optimization
This repository is dedicated to optimization from simple linear programming to advanced recent methods across literature.

**McCormick Envelope**
We use this reformulation whenever we are dealing with a bilinear term (like x.y). Introduce a new variable z and replace every x*y with it. And then, add these four constraints:

For the lower bound, we have:

<p align="center">$z \geq x^L y + y^L x - x^L y^L$<p>

<p align="center">$z \geq x^U y + y^U x - x^U y^U$<p>

For the upper bound, we have:

<p align="center">$z \leq x^U y + y^L x - x^U y^L$<p>

<p align="center">$z \leq x^L y + y^U x - x^L y^U$<p>

In this repository, I implemented this reformulation on a Pooling Problem.

To learn more about McCormick Envelope, take a look at [1] https://www.linkedin.com/pulse/mccormick-envelope-pooling-problem-parsa-nikpour-husnf/?trackingId=zBCtTMIDFC96mdrl%2BMtJxA%3D%3D and [2] https://optimization.cbe.cornell.edu/index.php?title=McCormick_envelopes.


  
**Generalized Disjunctive Programming** 

Disjunctive programming was first proposed by Balas in 1979 [1]. Then this method was generalized by Raman and Grossmann in 1994 [2] and is called "Generalized Disjunctive Programming (GDP)". In GDP, the constraints are in the form of propositional logic. This form of programming is widely used in chemical engineering, sequence and job-shop problems, and maintenance. Take a look at the following model taken from https://pyomo.readthedocs.io/en/6.8.0/modeling_extensions/gdp/concepts.html


![GDP](https://github.com/user-attachments/assets/d8d59d41-cc4f-4839-a069-906b85d85deb)

Two main reformulations are available for GDP: 1- Convex Hull and 2- Big M, which convex hull provides tighter reformulation than Big M. Alternatively, one can use M Big M and cutting plane reformulations, too. In the Linear GDP file, I used "Setf5 Instance", which is a job-shop problem. My code is based on https://jckantor.github.io/ND-Pyomo-Cookbook/notebooks/04.03-Job-Shop-Scheduling.html.

For nonlinear GDP, convex hull and Big M can be used too. However, instead of reformulating the problem, you can use Logic-based Outer Approximation, Global Logic-based Outer Approximation, Relaxation with Integer Cuts and Logic-based Branch-and-Bound to solve the optimization problem directly. In the Nonlinear-GDP file, I considered an arbitrary chemical processing problem with nonlinear objectives and constraints and solved it using the mentioned methods.










**References**

[1] Balas, E. , Disjunctive Programming , vol 5 , 1979 , pp 3-51

[2] Raman, R. and I.E. Grossmann, Modelling and Computational Techniques for Logic Based Integer Programming,vol 18, 1994, Computers and Chemical Engineering, pp 563
