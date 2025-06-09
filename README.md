# Flow_Over_A_Cylinder_LBM

# Flow Over A Cylinder - Lattice Boltzmann Method (LBM) 🚀

## Overview
This repository contains a Python implementation of the Lattice Boltzmann Method (LBM) for simulating fluid flow past a circular obstacle. The simulation visualizes velocity magnitude over time, demonstrating vortex shedding at moderate Reynolds numbers.

---

## Features
✅ D2Q9 Lattice for 2D flow simulation  
✅ Bounce-back boundary conditions for solid obstacles  
✅ Inlet velocity profile for flow initialization  
✅ Live visualization of velocity magnitude using matplotlib  
✅ Adjustable Reynolds number for different flow regimes  

---

## Installation

Clone the repository:
```bash
git clone https://github.com/yourusername/lbm-flow.git
cd lbm-flow
Install dependencies (ensure Python 3.x is installed):

bash
Copy
Edit
pip install numpy matplotlib
Usage
Run the simulation script:

bash
Copy
Edit
python lbm_simulation.py
By default, the simulation runs for 200,000 iterations. You can adjust parameters like domain size, velocity, and Reynolds number inside the script.

How It Works 🏎️
This simulation follows the Lattice Boltzmann Method (LBM) using the D2Q9 model:

1️⃣ Initialization:
Velocity field initialized with a uniform profile at the inlet.

Circular obstacle defined in the flow domain.

2️⃣ LBM Evolution:
Collision step: Uses the BGK model with relaxation parameter ω.

Streaming step: Distributes densities to neighboring nodes.

Boundary conditions:

Bounce-back for obstacles (solid walls)

Zou-He velocity BCs at the inlet

Free-flow BCs at the outlet

3️⃣ Visualization:
Velocity magnitude plotted in real-time.

Parameter Tuning 🎛️
Modify these variables in lbm_simulation.py to customize the simulation:

Parameter	Description	Default Value
Re	Reynolds number	110.0
nx, ny	Grid size (width × height)	420 × 180
maxIter	Simulation iterations	200000
uLB	Inlet velocity	0.04
cx, cy, r	Obstacle center and radius	nx//4, ny//2, ny//9

Example Output 📊
The simulation produces a velocity magnitude field visualizing vortex shedding behind the cylinder.

References & Further Reading 📚
Succi, S. (2001). The Lattice Boltzmann Equation for Fluid Dynamics and Beyond.

Krüger, T. et al. (2017). The Lattice Boltzmann Method: Principles and Practice.

Wikipedia: Lattice Boltzmann Method

License 📜
This project is licensed under the MIT License. Feel free to use and modify it.

Just replace `https://github.com/yourusername/lbm-flow.git` with your actual repo URL and paste this into your README.md.




