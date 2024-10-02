
# README for Training Code
This code is designed to train a neural network to predict the trajectories of agents in a collective motion model. It uses Physics-Informed Neural Networks (PINNs) to learn the interaction forces between agents based on their positions and velocities. The code is written in Python 3.7.0 and is built on PyTorch 1.10.1+cu111, utilizing CUDA for GPU acceleration if available.

## Requirements
Python: 3.7.0
PyTorch: 1.10.1+cu111
CUDA: GPU support is optional but recommended. Ensure that a compatible version of CUDA is installed.

## Libraries:
numpy
matplotlib
torch

## You can install the required packages using the following commands:
pip install torch==1.10.1+cu111 -f https://download.pytorch.org/whl/torch_stable.html
pip install numpy matplotlib


## Usage

### 1. Running the Training
To run the training process, simply execute the ipynb file. 
The model will be trained for up to 1000 epochs using the LBFGS optimizer, following an initial optimization with the Adam optimizer. 
The training process automatically stops if the loss values reach a stable point.

### 2. Adjusting Training Parameters
The code includes several adjustable hyperparameters that can be changed before running the training:

- r_a, r_b: These values determine the radius boundaries of the agent interaction. 
	Modify them to change the spatial scope of the agent interactions. 
	If modeling a ring pattern, please set r_a and r_b to the same value.
- int_range:  In the alignment mechanism, agents can only interact within a specified interaction range. 
	If you want to control this interaction range, adjust the int_range parameter.
- radius: When training for flocking behavior, you can modify the radius to control the maximum spatial extent of the flock.
- N (Number of Agents): To change the number of agents in the simulation, modify the variable N accordingly.
- Mill Type: When training a mill pattern, specify whether the type is "single" or "double" during the training process.
- Learning rates and epochs: You can adjust the number of epochs for both the Adam and LBFGS optimizers as well as the learning rate.
- Stopping Conditions: Early stopping is implemented if the loss value does not improve for 21 consecutive epochs. You can change the `patience` or `tolerance` variables to fine-tune this behavior.

###3. Selecting the Correct Jupyter Notebook for Different Patterns
For different collective motion patterns, open the corresponding .ipynb file for training:

Ring: Collective_motions_training_ring.ipynb
Clumps: Collective_motions_training_clumps.ipynb
Mill: Collective_motions_training_mill.ipynb
Ordered state: Collective_motions_training_ordered_state.ipynb
Flock: Collective_motions_training_flock.ipynb
Experimental data (non-isotropic, hierarchical): Collective_motions_training_real_data_non-isotropic.ipynb / Collective_motions_training_real_data_hierarchical.ipynb

## Output
Once the training is complete, the following parameters will be printed:
- Coefficients: lambda1-4
- Exponents: power1-3
If you want to verify the results through a numerical simulation, simply copy and paste the printed output into the simulation.ipynb file. 
For some patterns, parallel computation has been employed to speed up the calculation process, 
so make sure to use the simulation file named after the corresponding pattern type (e.g., Simulation_ring,clumps,mill.ipynb, Simulation_parallel_flock.ipynb, etc.).

Please note that the PINN is sensitive to the initialization process. 
If there are significant radius errors in the simulation results, retraining the model may be necessary to achieve more accurate predictions.

# Early Stopping Condition
Early stopping is implemented based on the following criteria:

If the loss value does not improve after 21 consecutive epochs.
If the difference in loss values is less than the specified tolerance of 1e-4.