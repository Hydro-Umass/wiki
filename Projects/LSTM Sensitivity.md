This is the main page for the LSTM Sensitivy project.

# Running on Unity

First follow the instructions at []() to set up the `uv` environment and the source code. 

We need this slurm script to start an experiment run
```bash
#!/bin/bash
#SBATCH --time=3:00:00
#SBATCH --nodes=1
#SBATCH --partition=gpu
#SBATCH --gpus-per-node=1
#SBATCH --constraint="vram48"
#SBATCH --mem=64g

module load cuda/12.8 cudnn/8.9.7.29-12-cuda12.8

/home/kandread_umass_edu/lstm/.venv/bin/python /home/kandread_umass_edu/lstm/experiments/exp1_forcings.py with nldas
```

Replace the paths in the command with your environment.

# Experiments:
We use the CAMELS dataset to conduct a sensitivity analysis of deep learning model (LSTM) for hydrologic applications along with VIC model aplication to have a base comparison. 

1. Different Forcings: 
Training and testing with all three type forcings. Such as DayMET-DayMET, Maurer-Maurer, NLDAS-NLDAS.

2. Hydrologic Reproducibility: 
Training with one type of forcings and testing with another type of forcings. Such as DayMET-Maurer, DayMET-NLDAS, Maurer-DayMET, Maurer-NLDAS, NLDAS-DayMET, NLDAS-Maurer.

3. Non-physical Actions:
The model input can be utilized in non-physical operations. Such as using zero precipitation instead of actual precipitation data.

4. Random and Systematic Perturbation: 
We can also introduce input perturbation by adding a random bias to precipitation. 

5. Sample Splits:
Training and testing data can be split in various ways, such as using only the dry season, only the wet season, or only extremes.

6. Limiting Information:
Training data can be modified or limited by removing precipitation data entirely. This experiment can not be applicable for VIC model.

7. Hyperparameter Analysis:
Model performance can be assessed under different model configurations.



