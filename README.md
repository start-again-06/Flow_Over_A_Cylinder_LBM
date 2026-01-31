# Flow Over a Cylinder  
## Fluid Flow Simulation using Lattice Boltzmann Method (LBM)

---

## System Overview
This repository implements a **2D Lattice Boltzmann Method (LBM)** solver to simulate incompressible fluid flow past a circular cylinder. The simulation captures **vortex shedding behavior** at moderate Reynolds numbers and provides real-time visualization of the **velocity magnitude field**.

The implementation is designed for numerical clarity, educational use, and easy parameter tuning.

---

## High-Level Architecture

### Computational Domain Layer
- Model: D2Q9 lattice (2D, 9 velocity directions)
- Rectangular computational grid
- Circular cylinder embedded as a solid obstacle
- Boolean mask used for solid nodes

---

### Initialization Layer
- Uniform inlet velocity profile
- Density field initialized to equilibrium
- Cylinder geometry defined using center and radius
- Reynolds number controls the flow regime

---

### LBM Core Solver Layer

#### Collision Step
- BGK (Bhatnagar–Gross–Krook) collision model
- Relaxation parameter (ω) derived from kinematic viscosity
- Distributions relax toward local equilibrium

#### Streaming Step
- Particle distributions streamed to neighboring lattice nodes
- Propagation based on D2Q9 discrete velocity set

---

### Boundary Condition Layer
- Inlet: Zou–He velocity boundary condition
- Outlet: Free-flow (zero-gradient) condition
- Cylinder: Bounce-back boundary (no-slip)
- Domain walls: Implicit no-slip via bounce-back

---

### Visualization Layer
- Real-time plotting using `matplotlib`
- Velocity magnitude field updated periodically
- Clearly visualizes wake formation and vortex shedding

---

## Parameter Configuration

| Parameter | Description | Default Value |
|---------|------------|---------------|
| Re | Reynolds number | 110.0 |
| nx, ny | Grid resolution (width × height) | 420 × 180 |
| maxIter | Number of iterations | 200000 |
| uLB | Inlet velocity magnitude | 0.04 |
| cx, cy, r | Cylinder center (x, y) and radius | nx//4, ny//2, ny//9 |

All parameters can be modified inside `lbm_simulation.py`.

---

## Execution Flow
1. Initialize lattice, density, and velocity fields  
2. Define circular obstacle geometry  
3. Apply inlet and outlet boundary conditions  
4. Perform collision step (BGK relaxation)  
5. Perform streaming step  
6. Enforce bounce-back at obstacle nodes  
7. Compute macroscopic velocity field  
8. Visualize velocity magnitude  

---

## Dependencies
- Python 3.x  
- NumPy  
- Matplotlib  

## Example Output
- Velocity magnitude contours showing vortex shedding  
- Alternating wake structures downstream of the cylinder  
- Stable laminar-to-unsteady transition at moderate Reynolds numbers  

---

## Scalability & Extensibility
- Extendable to moving or deformable boundaries  
- Can include force coefficient computation (drag and lift: Cd, Cl)  
- Suitable for CFD education and research prototyping  
- Performance can be improved using Numba, CuPy, or GPU acceleration  

---

## Applications
- Computational Fluid Dynamics (CFD) education  
- Wake flow and vortex shedding analysis  
- Validation and benchmarking of LBM solvers  
- Research-oriented fluid simulation prototyping  

---

## References
- Succi, S. (2001). *The Lattice Boltzmann Equation for Fluid Dynamics and Beyond*  
- Krüger, T. et al. (2017). *The Lattice Boltzmann Method: Principles and Practice*  
- Wikipedia: Lattice Boltzmann Method  

---

## License
MIT License. Free to use, modify, and distribute for academic and research purposes.


