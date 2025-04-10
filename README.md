
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
- Euler’s Method
  \begin{equation}
\frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0
\end{equation}

The Euler method provides an iterative numerical solution using the update formula:

\begin{equation}
y_{n+1} = y_n + h \cdot f(t_n, y_n)
\end{equation}
  
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
