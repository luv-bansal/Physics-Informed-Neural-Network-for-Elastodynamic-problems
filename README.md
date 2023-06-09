# Physics-Informed-Neural-Network-for-Elastodynamic-problems
<p>
PINN is used to solve non-linear partial differential physics equation using neural network. In this project, we are solving elasticity problem which is 2nd order differential equation and compare its result with FEM (numercal method to solve equation).
</p>

<p>
  This is a research project done under proffesor Dr. Nilanjan Malik. 
 </p> 


## Description for each folder
- **Elastodynamic - basic problem**: Training script for finding stresses and displacements in plate under constant load.
- **Elastodynamic - plate hole problem**: Training script for finding stresses and displacements in plate with hole at center under constant load.
- **Elastodynamic - time varying problem**: Training script for finding stresses and displacements in plate under dynamic(sinusoidal) loading. 
- **Elastodynamic - time varying with hole problem**: Training script for finding stresses and displacements in plate with hole at center under dynamic(sinusoidal) loading.  


## PINN

PINN (Physics-Informed Neural Networks) is a powerful technique that combines deep learning with physics-based modeling to accurately predict and simulate complex physical systems. By incorporating known physical laws and constraints into the neural network architecture, PINNs are able to leverage the strengths of both approaches and achieve superior accuracy compared to traditional numerical methods. PINNs have been successfully applied in a variety of fields, including fluid dynamics, solid mechanics, and electromagnetics. This GitHub repository contains code and resources for implementing PINNs and conducting research in this exciting and rapidly growing field.

$L = L_{\text{data}} + \lambda L_{\text{physics}}$

where $L_{\text{data}}$ is the data-driven loss term, $L_{\text{physics}}$ is the physics-based loss term, and $\lambda$ is a regularization parameter that controls the balance between these two terms. The data-driven loss term measures the discrepancy between the predictions of the neural network and the available data, while the physics-based loss term enforces the physical constraints of the problem being solved. The goal of the PINN is to minimize this loss function with respect to the model parameters in order to obtain accurate predictions and simulations of the physical system of interest.

## Problem statement

> Defected plate under periodic uni-axial tension

A two-dimensional plane stress problem, i.e., a defected plate under uni-axial tension, is considered in this example. The total length of the square plate is 1.0 m while the radius of the circular defection located in the center is 0.1 m. Due to the symmetry of the problem, only a quarter plate is simulated (see Fig). The Young’s modulus and Poisson’s ratio of the plate are 20 MPa and 0.25, respectively. A uni-axial normal traction Tn(t) is applied on the right edge as shown in Fig.

![image](https://user-images.githubusercontent.com/70321430/233512798-b496170b-6bf2-49e2-9070-bfe3514b8c16.png)

## Elasticity Equation

> Governing equation 

$\nabla \cdot \boldsymbol{\sigma} + \mathbf{f} = \mathbf{0}$

where $\boldsymbol{\sigma}$ is the stress tensor, $\mathbf{f}$ is the body force vector, and $\nabla$ is the divergence operator. This equation expresses the balance of forces in a deformable body, stating that the divergence of the stress tensor plus the body force vector equals zero. In continuum mechanics, this equation is often used to describe the behavior of solids under deformation, and is a fundamental equation in the field of elasticity.


> In terms of displacement, Hooke's law can be expressed as:

$\boldsymbol{\sigma} = \mathbf{C} : \boldsymbol{\epsilon} = \mathbf{C} : \left( \frac{1}{2} (\nabla \boldsymbol{u} + \nabla \boldsymbol{u}^T ) \right)$

where $\mathbf{C}$ is the elastic modulus tensor, and $\boldsymbol{\epsilon}$ is the strain tensor. The colon symbol represents the tensor inner product.

> By substituting the expression for stress in terms of displacement into the elasticity equation, we obtain the following expression:

$\nabla \cdot (\mathbf{C} : \left( \frac{1}{2} (\nabla \boldsymbol{u} + \nabla \boldsymbol{u}^T ) \right)) + \mathbf{f} = \mathbf{0}$

This equation can be used to solve for the displacement field in a deformable body subjected to external forces and boundary conditions, given the elastic modulus tensor and body force vector.

Therefore, we are solving 2nd order 3d partial differential equation.







## Results overview
Refresh to reload the gifs
>Stresses in Defected plate under cyclic load (top: PINN; middle: FEM; bottom: error)


<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20comparison.gif" width="500" />

>Displacement(u: displacement in x-direction & v: displacement in y-direction) in Defected plate under cyclic load (top: PINN; middle: FEM; bottom: error)

<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/Displacement%20comparison.gif" width="500" />

>Displacement near hole

<p >
<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20near%20hole%20(3).jpg" width="300" />

<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20near%20hole%20(1).png" width="300" />
</p>

>Stresses near hole

<p float="left">
<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20near%20hole%20(4).jpg" width="300" />

<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20near%20hole%20(1).jpg" width="300" />

<img src="https://github.com/luv-bansal/Physics-Informed-Neural-Network-for-Elastodynamic-problems/blob/main/Elastodynamic%20-%20time%20varying%20with%20hole%20problem/results/stress%20near%20hole%20(2).jpg" width="300" />
</p>

## Reference paper 

[Chengping Rao, Hao Sun and Yang Liu. Physics informed deep learning for computational elastodynamics without labeled data.](https://arxiv.org/abs/2006.08472)
