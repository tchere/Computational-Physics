
# 🧮 Computational Physics 


## 📚 Objective

To equip us with practical computational tools for solving physical problems, including numerical methods for ODEs and PDEs, and advanced techniques like exact diagonalization for quantum many-body systems.


## 🧠 What I have learned
- Classical equation of motion (pendulum and wave problem solved by numerical ODE, such as Euler method, Leap frog and 4th order Runge Kutta method on harmonic oscillator)
- Relaxation method to solve PDE (Jacobi Relaxation)
- Method for solving space-time PDE ( Forward time centred space discretisation (FTCS) and CTCS scheme method and Lax-Wendroff method)
- Quantum many body phsyics ( Exact diagonalization) 

---

## 📘 Assignment description



## 🔧 Assignment 1 

The first part of Assignment 1 is to use 3 numerical method (Euler velocity verlet and Runge Ketta method to calculate the orbit of the Earth. The fundamental procedure of the method is given the initial boundary condition and calculate the next iternation data, we would like to see which method can have a high precision to complete one orbit. The introduction of the method are written as follow:

- Euler’s Method (The first order forward differentiation)
  
$$
\frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0
$$

The update rule is given by:

$$
y_{n+1} = y_n + h \cdot f(t_n, y_n)
$$

- Velocity Verlet method

$$
x_{n+1} = x_n + v_n h + \frac{1}{2} a_n h^2
$$

$$
a_{n+1} = a(x_{n+1}, t_{n+1})
$$

$$
v_{n+1} = v_n + \frac{1}{2} (a_n + a_{n+1}) h
$$

- Runge-Kutta Methods (RK4)

$$
k_1 = f(t_n, y_n)
$$

$$
k_2 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_1\right)
$$

$$
k_3 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_2\right)
$$

$$
k_4 = f(t_n + h, y_n + hk_3)
$$

$$
y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)
$$

By comparsion, Runge Kutta method perform the grestest performence, since the Runge Kutta method has the lowest trancation error among those method under the same iteration time step. 

The latter part give the proof of Kepler's second law, which state that the Sun sweeps equal areas of space during equal time intervals as the planet orbits. If we express it in equation: 

$$
\frac{dA}{dt} = \frac{1}{2}rv
$$

In the code, we prove that each second of 1/2 rv result respond to similar value, which means that there are similar ratio of dA/dt, which prove the Kelper's second law.

--- 

## 🔧 Assignment 2

The aim of this assignment is to compare 3 different relaxiation method to solve the Poisson equation (potential problem), and use Lax and Lax-Wendroff method to solve space-time PDE.

## Poisson Equation 
The 3 numerical method I introduce here follow the grid (lattice) updated structure, which means that each updated point will appear 4 nearest neighbour.

Jacobi Relaxation 

$$
\phi(\vec{r}) = \frac{1}{2d} \sum_{i=1}^{d} \left( \phi(\vec{r} + h \vec{e}_i) + \phi(\vec{r} - h \vec{e}_i) \right) + \frac{h^2}{2d \varepsilon_0} \rho(\vec{r})
$$

Jacobi Relaxation method update the iteration using the current 4 neighbour, the below is the pseudocode for Jocobi Relaxation.


Gauss-Seidel Relaxation


Gauss-Seidel Relaxation Equation


The Gauss-Seidel update rule for the 2D Poisson equation is:

$$
\phi_{i,j}^{(k+1)} = \frac{1}{4} \left( \phi_{i+1,j}^{(k)} + \phi_{i-1,j}^{(k+1)} + \phi_{i,j+1}^{(k)} + \phi_{i,j-1}^{(k+1)} - h^2 f_{i,j} \right)
$$



The first updated iteration need to be calculated by Jacobi method, the updated rule of Gauss-Seidel method adopt the current-neighbour method, which use the updated data point immediately. 

Successive Overrelaxation (SOR) Method

The update rule for the SOR method is:

$$
\phi(\vec{r}) \rightarrow (1 - \omega)\phi(\vec{r}) + \omega \left( \frac{1}{2d} \sum_{i=1}^{d} \left( \phi(\vec{r} + h \vec{e}_i) + \phi(\vec{r} - h \vec{e}_i) \right) + \frac{h^2}{2d \varepsilon_0} \rho(\vec{r}) \right)
$$



SOR is a faster version of Gauss-Seidel that uses a weighted average to accelerate convergence. We need to choose the optimal weighting to do the update.

To sum up, The SOR method give the highest efficiency among the 3 method, we use 3 method to plot the 3d graph in the specific boundary condition (star and cylindrical boundary condition).


For the latter part of the assignment, we try to simulate the motion of tsunami, the equation of it is:

$$
\frac{\partial}{\partial t}
\begin{pmatrix}
h \\
u
\end{pmatrix}
= - \frac{\partial}{\partial x}
\begin{pmatrix}
(h - b) u \\
\frac{1}{2} u^2 + g h
\end{pmatrix}
$$

## space-time PDE

We are solving: 

$$
\frac{\partial u}{\partial t} = -\frac{\partial F(u)}{\partial x}
$$

For numerical method, we adopt the Lax and Lax Wendroff method, in this course, we had also been taught with FTCS method to solve the space-time PDE, while, the solution of the FTCS scheme is not stable, the detail explaination have been written in the assignment 2. 

For Lax method, it is given: 

$$
u(n+1, r) = \frac{1}{2} \left( u(n, r+1) + u(n, r-1) \right)
-\frac{c \tau}{2h} \left( u(n, r+1) - u(n, r-1) \right)
$$

The idea of Lax method is still the exapansion of the first order foward differentiation both side, while the advantage of this method numerical diffusion added in the first term, which gives more stable prediction. 

For Lax Wendroff method, it is given: 


$$
u_i^{n+1} = u_i^n - \frac{a \Delta t}{2 \Delta x}(u_{i+1}^n - u_{i-1}^n)
+\frac{a^2 \Delta t^2}{2 \Delta x^2}(u_{i+1}^n - 2u_i^n + u_{i-1}^n)
$$

Lax-Wendroff method adopt the second order order approximation, it is more accurate than the Lax method but more running time. 

The equation of tsunami is a 2 variable space-time PDE, we can solve it as two 1-D PDE which named the variable as x and y axis to solve the problem, the animation is shown in the last part of question 4.

--- 

## 🔧 Assignment 3

- The follow approach tried to solve the time-independent schrodinger equation.

Wavefunction Representation and Hamiltonian Matrix

 Wavefunction vector:

$$
\Psi =
\begin{pmatrix}
\psi(1) \\
\psi(2) \\
\psi(3) \\
\vdots \\
\psi(N-1) \\
\psi(N)
\end{pmatrix}
$$

With boundary conditions:

$$
\psi(0) = \psi(N+1) = 0
$$

---

Matrices:

**Matrix A:**

$$
\mathbf{A} = \frac{1}{h^2} \left( \mathbb{I}_{-1} - 2\mathbb{I}_0 + \mathbb{I}_1 \right)
$$

**Matrix B:**

$$
\mathbf{B} = \frac{1}{12} \left( \mathbb{I}_{-1} + 10\mathbb{I}_0 + \mathbb{I}_1 \right)
$$

**Potential matrix \( \nu \):**

$$
\nu =
\begin{pmatrix}
\nu_1 & 0 & \cdots & 0 \\
0 & \nu_2 & \cdots & 0 \\
\vdots & 0 & \ddots & \vdots \\
0 & 0 & \cdots & \nu_N
\end{pmatrix}
$$

---

Hamiltonian Equation:

$$
\left( -\frac{1}{\gamma^2} \mathbf{B}^{-1} \mathbf{A} + \nu \right) \Psi = \epsilon \Psi
$$

---


We apply the modified Hamiltonain to find out the eigenvalue of the wavefunction, which the eigenvalue is the energy itself. 

The latter part of assignment 3, we use the Crank-Nicolson Scheme to compete the schrodinger equation (PDE).


Consider the time-dependent Schrödinger equation:

$$
i\hbar \frac{\partial}{\partial t} \psi(t, x) = H(x) \psi(t, x)
$$

---

Using the **Crank–Nicolson scheme**, the equation can be written as:

$$
i\hbar \frac{\psi_r^{n+1} - \psi_r^n}{\tau} = \sum_{s=1}^{N} H_{r,s} \cdot \frac{1}{2} \left( \psi_s^n + \psi_s^{n+1} \right)
$$

---

With:

$$
H_{r,s} = -\frac{\hbar^2}{2m} \cdot \frac{\delta_{r+1,s} + \delta_{r-1,s} - 2\delta_{r,s}}{h^2} + V(x_r)\delta_{r,s}
$$

---

Further:

$$
\psi^{n+1} = \left( 1 + \frac{i\tau}{2\hbar} H \right)^{-1} \left( 1 - \frac{i\tau}{2\hbar} H \right) \psi^n
$$

---

Initial condition:

$$
\psi(t = 0, x) = \frac{1}{\sqrt{\sigma_0 \sqrt{2\pi}}} e^{ik_0(x - x_0)} e^{-\frac{(x - x_0)^2}{2\sigma_0^2}}
$$

Which the hamiltonian can written as:

$$
H_{r,s} = -\frac{\hbar^2}{2m} \cdot \frac{\delta_{r+1,s} + \delta_{r-1,s} - 2\delta_{r,s}}{h^2} + V(r)\delta_{r,s}
$$

We can find out the list of all psi, then we can plot the probability distribution of the system which is the square term of psi.

--- 

## Assignment 4

Application of exact diagonlization to find energy eigen function.

We are now considering the problem in Heisenberg model. 

## 🧮 Heisenberg Hamiltonian for Two Spins


The Hamiltonian is:

### 🔧 Action of \( H \) on Basis States

$$
H \left| \uparrow \uparrow \right\rangle = \frac{J}{4} \left| \uparrow \uparrow \right\rangle
$$

$$
H \left| \downarrow \downarrow \right\rangle = \frac{J}{4} \left| \downarrow \downarrow \right\rangle
$$

$$
H \left| \uparrow \downarrow \right\rangle  
= \frac{J}{2} \left| \downarrow \uparrow \right\rangle - \frac{J}{4} \left| \uparrow \downarrow \right\rangle
$$

$$
H \left| \downarrow \uparrow \right\rangle  
= \frac{J}{2} \left| \uparrow \downarrow \right\rangle - \frac{J}{4} \left| \downarrow \uparrow \right\rangle
$$

---

### 📐 Matrix Elements

$$
\langle \uparrow \uparrow | H | \uparrow \uparrow \rangle = \frac{J}{4}
\qquad
\langle \downarrow \downarrow | H | \downarrow \downarrow \rangle = \frac{J}{4}
$$

$$
\langle \uparrow \downarrow | H | \uparrow \downarrow \rangle = -\frac{J}{4}
\qquad
\langle \downarrow \uparrow | H | \downarrow \uparrow \rangle = -\frac{J}{4}
$$

$$
\langle \uparrow \downarrow | H | \downarrow \uparrow \rangle = \frac{J}{2}
\qquad
\langle \downarrow \uparrow | H | \uparrow \downarrow \rangle = \frac{J}{2}
$$

---

### 🧾 Hamiltonian Matrix


The matrix form of H is:

$$
H = J \begin{pmatrix}
\frac{1}{4} & 0 & 0 & 0 \\
0 & -\frac{1}{4} & \frac{1}{2} & 0 \\
0 & \frac{1}{2} & -\frac{1}{4} & 0 \\
0 & 0 & 0 & \frac{1}{4}
\end{pmatrix}
$$




Exact diagonalization is a specific approach that to find out the eigenvalue of each spin operator and they manifest in the Hamililtonian matrix. We find out the eigenvalue of the Hamililtonian matrix which corrspond to the energy density function to Henserberg model. This method is only cater for specific model like Hensenberg model which the Hamilitonian matrix can be block-diagonlized and the Hamilitonian is symmetric. 

We make use of exact diagonlization to calculate the ground state energy of a 10 x 10 Henserberg model. 

The latter part of the Assignment is to calculate the Renyi Entropy and von Neumann entropy for N=10.


The equation of Renyi Entropy is:

$$
S_A^{(n)} = \frac{1}{1 - n} \ln \left( \mathrm{Tr} \left( \rho_A^n \right) \right).
$$

While the von Neumann entropy is:

$$
S_A^{\mathrm{vN}} = -\mathrm{Tr}(\rho_A \ln \rho_A)
$$

The code in my assignment follow the construction of the equation. For the reduced density matrix, it is the dot product of the eigenvector of Hamiltonian Matrix, the code have shown that there is a 10x10 reduced density matrix nad plug in the fomula to calculate the Renyi and von Neumann entropy. The graph of the diestribution of the entropy is also shown in the source code. 








