# Particle-Swarm-Optimisation-using-OpenMPI

# Particle Swarm Optimization using OpenMPI

This repository implements **Particle Swarm Optimization (PSO)** using **OpenMPI**, a powerful library for parallel programming. PSO is a population-based stochastic optimization technique inspired by the social behavior of birds and fish. By leveraging OpenMPI, this implementation demonstrates how distributed computing can significantly enhance the efficiency and scalability of PSO for solving complex optimization problems.

---

## Table of Contents

1. [Introduction](#introduction)  
2. [Features](#features)  
3. [Setup](#setup)  
4. [Usage](#usage)  
5. [Example Output](#example-output)  
6. [Performance](#performance)  
7. [Limitations](#limitations)  
8. [References](#references)  
9. [Contributing](#contributing)  
10. [License](#license)  

---

## Introduction

Particle Swarm Optimization (PSO) is an optimization algorithm that uses a swarm of particles (solutions) to explore the search space. Each particle adjusts its position based on its experience and that of its neighbors. This repository implements PSO with **OpenMPI**, allowing the computational workload to be distributed across multiple processors or nodes. The goal is to showcase how parallelization can reduce computation time for large-scale optimization problems.

### Key Concepts of PSO

- **Particles**: Each particle represents a potential solution.  
- **Velocity Update**: Each particle adjusts its velocity based on personal and global bests.  
- **Position Update**: The particle moves to a new position based on the updated velocity.  
- **Fitness Function**: Evaluates the quality of a particle's solution.  

---

## Features

- **Parallelized Swarm Evaluation**: Distributes fitness function evaluations across multiple processors.  
- **Scalable Implementation**: Suitable for large-scale optimization problems with high-dimensional search spaces.  
- **Customizable Fitness Functions**: Easily modify the objective function to suit your problem.  
- **Configurable Parameters**: Tune swarm size, velocity coefficients, and iterations.  

---

## Setup

### Prerequisites

- **OpenMPI**: Install OpenMPI for parallel computation.  
- **C Compiler**: GCC or any compatible C compiler supporting MPI.  
- **Linux/Unix Environment**: For optimal compatibility.  

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Particle-Swarm-Optimisation-using-OpenMPI.git
   cd Particle-Swarm-Optimisation-using-OpenMPI

### Usage
mpirun -np <num_processes> ./pso <input_file>

Example Config:
swarm_size=50
dimensions=10
iterations=100
inertia_weight=0.7
cognitive_coeff=1.5
social_coeff=1.5
bounds=-10,10

Output:
Best solution: [x1, x2, ..., xn]
Best fitness: 0.00123
Starting Particle Swarm Optimization...
Swarm Size: 50
Dimensions: 10
Iterations: 100

Iteration 1: Best Fitness = 10.234
Iteration 2: Best Fitness = 5.678
...
Final Best Solution: [1.234, 3.456, ..., 0.987]
Final Best Fitness: 0.00012
Optimization Complete.

### Performance

Using OpenMPI, this implementation achieves significant speedups by parallelizing fitness evaluations. The performance gain is particularly noticeable for:

High-dimensional search spaces.
Expensive fitness functions.
Large swarm sizes.

### Limitations

Fitness Function Parallelization: Only the fitness evaluation is parallelized. Other components run sequentially.
Hardware Dependency: Performance depends on the number of available processors.
Network Latency: Distributed systems may face delays in inter-process communication.

### References

Kennedy, J., & Eberhart, R.: Particle Swarm Optimization, Proceedings of IEEE ICNN (1995).
OpenMPI Documentation: https://www.open-mpi.org/
PSO Theory and Applications: https://en.wikipedia.org/wiki/Particle_swarm_optimization   
