
# 🧮 Computational Physics 


## 📚 Objective

To equip us with practical computational tools for solving physical problems, including numerical methods for ODEs and PDEs, and advanced techniques like exact diagonalization and Monte Carlo methods for quantum many-body systems.


## 🧠 What I have learned
- Classical equation of motion (pendulum and wave problem solved by numerical ODE, such as Euler method, Leap frog and 4th order Runge Kutta method on harmonic oscillator)
- Relaxation method to solve PDE (Jacobi Relaxation)
- Method for solving space-time PDE ( Forward time centred space discretisation (FTCS) and CTCS scheme method and Lax-Wendroff method)
- Quantum many body phsyics ( Exact diagonalization) 
- Classical and quantum Monte Carol Method 

---

## 📘 Assignment description



### 🔧 Assignment 1 

The first part of Assignment 1 is to use 3 numerical method (Euler velocity verlet and Runge Ketta method to calculate the orbit of the Earth, we would like to see which method can have a high precision to complete one orbit. The introduction of the method are written as follow:

- Euler’s Method (The first order forward differentiation)
$$
\frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0
$$

The update rule is given by:

$$
y_{n+1} = y_n + h \cdot f(t_n, y_n)
$$

Where:
- \( y_n \) is the approximation of the solution at time \( t_n \),
- \( h \) is the time step size,
- \( f(t_n, y_n) \) is the derivative evaluated at \( (t_n, y_n) \).

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



  
- Runge-Kutta Methods (RK2, RK4)
- Adaptive Step Size
- Phase Space Analysis

### 📘 Applications
- Simple Harmonic Oscillator
- Damped/Driven Oscillators
- Two-body gravitational problem
- Chaos: Lorenz system

---

## 🌊 Module 2: Numerical PDEs

This module introduces techniques to solve **partial differential equations (PDEs)** relevant in heat flow, wave propagation, and quantum mechanics.

### 🔧 Topics
- Finite Difference Method (FDM)
- Crank-Nicolson Scheme
- Stability and Convergence
- Boundary and Initial Conditions

### 📘 Applications
- Heat Equation (1D, 2D)
- Wave Equation
- Schrödinger Equation (Time-dependent)

---

## 🧬 Module 3: Exact Diagonalization & Entropy

This module explores solving quantum mechanical systems using **exact diagonalization** and applying it to study **quantum entanglement entropy**.

### 🔧 Topics
- Hilbert space construction
- Fermionic/bosonic occupation basis
- Hamiltonian matrix construction
- Eigenvalue problem solvers (`numpy.linalg.eigh`)

### 📘 Applications
- Tight-binding model (2D lattice)
- Many-body Hamiltonians
- Entanglement entropy:
  - Von Neumann entropy
  - Renyi entropy
  - Subsystem tracing

---

## 📦 Tools and Libraries

- Python 3.x
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebooks (for interactive coding)
- (Optional) QuTiP for quantum systems

---

## 📁 Repository Structure
