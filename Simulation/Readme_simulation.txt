# README for Simulation Code

This code is used to simulate the trajectories of agents in a collective motion model based on the trained coefficients from a Physics-Informed Neural Network (PINN). 

## Requirements

The following Python libraries are required to run the simulation:

- Python: 3.7+
- Libraries:
  - numpy
  - matplotlib
  - scipy (version 1.7.3)
  - IPython

You can install the required libraries using the following command:
pip install numpy matplotlib scipy==1.7.3 ipython

## Usage
### 1. Preparing for Simulation
Before running the simulation, you need to input the following parameters:

- N: The number of agents. Default is set to 40 agents, but you can adjust it as needed.
- Coefficients: Enter the values for \( \lambda_1 \), \( \lambda_2 \), \( \lambda_3 \), and \( \lambda_4 \) (these are the trained interaction coefficients).
- Exponents: Enter the values for \( power_1 \), \( power_2 \), and \( power_3 \) (these represent the exponents in the interaction forces).

### 2. Running the Simulation
Once you've input the number of agents, the coefficients, and the exponents, you can run the simulation by executing all cells in the Jupyter notebook.
For different cases of collective motion, open the corresponding .ipynb file:

Ring, clumps, mill: Simulation_ring,clumps,mill.ipynb
Ordered state: Simulation_parallel_ordered_state.ipynb
Flock: Simulation_parallel_flock.ipynb
Experimental data (non-isotropic, hierarchical): Simulation_parallel_experimental_data_hierarchical.ipynb / Simulation_parallel_experimental_data_non-isotropic.ipynb
Transition: Simulation_parallel_transition.ipynb
Non-homogeneous: Simulation_parallel_non-homogeneous.ipynb


### 3. Key Variables

- v0: The reference velocity for the self-propelled particles.
- T: The total time of the simulation.
- dt: The time step size for the evaluation of simulation.

### 4. Running the Animation
The notebook uses `matplotlib.animation` to visualize the agent trajectories. 
After running the simulation, the animation will be displayed directly in the Jupyter notebook using the `HTML` function.

# README for Simulation Code

This code is used to simulate the trajectories of agents in a collective motion model based on the trained coefficients from a Physics-Informed Neural Network (PINN). 

## Requirements

The following Python libraries are required to run the simulation:

- Python: 3.7+
- Libraries:
  - numpy
  - matplotlib
  - scipy (version 1.7.3)
  - IPython

You can install the required libraries using the following command:
pip install numpy matplotlib scipy==1.7.3 ipython

## Usage
### 1. Preparing for Simulation
Before running the simulation, you need to input the following parameters:

- N: The number of agents. Default is set to 40 agents, but you can adjust it as needed.
- Coefficients: Enter the values for \( \lambda_1 \), \( \lambda_2 \), \( \lambda_3 \), and \( \lambda_4 \) (these are the trained interaction coefficients).
- Exponents: Enter the values for \( power_1 \), \( power_2 \), and \( power_3 \) (these represent the exponents in the interaction forces).

### 2. Running the Simulation
Once you've input the number of agents, the coefficients, and the exponents, you can run the simulation by executing all cells in the Jupyter notebook.
For different cases of collective motion, open the corresponding .ipynb file:

Ring, clumps, mill: Simulation_ring,clumps,mill.ipynb
Ordered state: Simulation_parallel_ordered_state.ipynb
Flock: Simulation_parallel_flock.ipynb
Experimental data (non-isotropic, hierarchical): Simulation_parallel_experimental_data_hierarchical.ipynb / Simulation_parallel_experimental_data_non-isotropic.ipynb
Transition: Simulation_parallel_transition.ipynb
Non-homogeneous: Simulation_parallel_non-homogeneous.ipynb


### 3. Key Variables

- v0: The reference velocity for the self-propelled particles.
- T: The total time of the simulation.
- dt: The time step size for the evaluation of simulation.

### 4. Running the Animation
The notebook uses `matplotlib.animation` to visualize the agent trajectories. 
After running the simulation, the animation will be displayed directly in the Jupyter notebook using the `HTML` function.

**If you encounter a codec error when saving the video or viewing it in HTML, you may need to install the necessary codecs (e.g., ffmpeg) for proper video rendering.
https://ffmpeg.org/download.html