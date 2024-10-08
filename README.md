![fig_github](https://github.com/user-attachments/assets/52756efe-4177-4404-84fc-d0226e7ea0ea)


# Parametric kernel-based dynamic mode decomposition using deep learning


This repository contains the methods and techniques implemented in the context of the thesis
research project of MSc in Computational Science at the University of Amsterdam.





In this work, a non-intrusive parametric surrogate model is presented, able to provide
temporal and parametric predictions for systems characterized by high state dimension and nonlinear
behavior. In detail, a parametrization algorithm is developed to extend the kernel-based
LANDO framework (Baddoo et al., [2022](https://royalsocietypublishing.org/doi/full/10.1098/rspa.2021.0830)) to a parametric format (parametric LANDO) using regression techniques. 
Additionally, an adaptive sampling technique based on deep ensemble
learning is developed, to smartly explore the parameter space and extract the most informative 
set of samples for the training of parametric LANDO. We showcase the effectiveness
of the proposed parametric surrogate model in predicting the parametric dynamics of
three numerical problems with nonlinear behavior; namely the Lotka-Volterra model, a
2D heat equation, and the Allen-Cahn equation


## Experiments

Several experiments are performed, regarding the application of the parametric surrogate model in the three aforementioned numerical problems. 
Additionally, we perform experiments to test the efficiency of the developed active learning technique. 

### Lotka-Volterra model
To perform the experiments regarding the application of parametric LANDO in the Lotka-Volterra model, the following python files should be run:

* `Experiments_1D.py` (The parameter space is one-dimensional)
* `Experiments_2D.py` (The parameter space is two-dimensional)
* `Experiment_RBF_vs_NN.py` (Compare the performance of different regression techniques)

To perform active learning in this system, the `Experiments_ActiveLearning.py` file should be run.



### Heat Equation 

The snapshot data for the training of the parametric framework in this case are generated with the finite element method (FEM). 
The implementation of the finite element simulation is based on the open source software [FreeFEM](https://freefem.org/). 

To generate the numerical data, please run the `Data_Generation.py`, `Heat_problem_thesis.edp`, and `Data_Preprocessing.py` files in that order. 
Subsequently, parametric LANDO can be employed to approximate the parametric dynamics of this system with the `Experiments_DiffTimes.py` file. 
As a last step, run the `Visualization.edp` file to obtain the .vtk visualisations of the reference solutions, predicted solutions, and prediction errors of the parametric surrogate model for several parametric instances. 



### Allen-Cahn equation

To generate the snapshot data, run the `Data_Generation.py`. 
To obtain results from the application of parametric LANDO in this system, run the `Experiments_DiffTimes.py`, in the folder of the Allen-Cahn equation. 
Additionally, to explore the 2D parameter space using adaptive sampling, the `Experiments_ActiveLearning.py` should be run.




### Important Notes:
* In order to run the aforementioned files, please change the names of the directories in the code, to save the results and figures in your local device.
* Note that FEM simulation for data generation of the heat equation, and the active learning experiments are computationally expensive. Running these files might take a long time

