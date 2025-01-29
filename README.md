# Flow_Over_A_Cylinder_LBM

Lattice Boltzmann Method (LBM) - Flow Around a Cylinder 🚀
Overview
This repository contains a Python implementation of the Lattice Boltzmann Method (LBM) for simulating fluid flow past a circular obstacle. The simulation visualizes velocity magnitude over time, demonstrating vortex shedding at moderate Reynolds numbers.

<p align="center"> <img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Vortex-street-animation.gif" width="400"/> </p>
Features
✅ D2Q9 Lattice for 2D flow simulation
✅ Bounce-back boundary conditions for solid obstacles
✅ Inlet velocity profile for flow initialization
✅ Live visualization of velocity magnitude using matplotlib
✅ Adjustable Reynolds number for different flow regimes

Installation
1. Clone the Repository
bash
Copy
Edit
git clone [https://github.com/yourusername/lbm-flow.git](url)
cd lbm-flow
2. Install Dependencies
Ensure you have Python 3.x installed, then install the required packages:

bash
Copy
Edit
[pip install numpy matplotlib](url)
Usage
Run the script to start the simulation:

bash
Copy
Edit
python lbm_simulation.py
By default, the simulation runs for 200,000 iterations. You can adjust parameters like domain size, velocity, and Reynolds number inside the script.

How It Works 🏎️
This simulation follows the Lattice Boltzmann Method (LBM) using the D2Q9 model:

<p align="center"> <img src="https://upload.wikimedia.org/wikipedia/commons/2/28/D2Q9%2C_velocity_set.png" width="300"/> </p>
1️⃣ Initialization:

The velocity field is initialized with a uniform profile at the inlet.
A circular obstacle is defined in the flow domain.

2️⃣ LBM Evolution:

Collision step: Uses the BGK model with relaxation parameter ω.
Streaming step: Distributes densities to neighboring nodes.
Boundary conditions:
Bounce-back for obstacles (solid walls).
Zou-He velocity BCs at the inlet.
Free-flow BCs at the outlet.

3️⃣ Visualization:

The velocity magnitude is plotted in real time.
Parameter Tuning 🎛️
Modify these variables in lbm_simulation.py to customize the simulation:

Parameter	Description	Default Value
Re	Reynolds number	110.0
nx, ny	Grid size (width × height)	420 × 180
maxIter	Simulation iterations	200000
uLB	Inlet velocity	0.04
cx, cy, r	Obstacle center and radius	nx//4, ny//2, ny//9
Example Output 📊
The simulation produces a velocity magnitude field:

<p align="center"> <img src="https://upload.wikimedia.org/wikipedia/commons/5/5b/Vortex-shedding.gif" width="400"/> </p>
References & Further Reading 📚
Succi, S. (2001). The Lattice Boltzmann Equation for Fluid Dynamics and Beyond.
Krüger, T. et al. (2017). The Lattice Boltzmann Method: Principles and Practice.
Wikipedia: Lattice Boltzmann Method
License 📜
This project is licensed under the MIT License. Feel free to use and modify it.
