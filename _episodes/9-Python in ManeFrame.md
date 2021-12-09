---
title: "Python workflow in ManeFrame"
teaching: 10
exercises: 0
questions:
- "How to run Python in ManeFrame"
objectives:
- "Learn how to run Python in ManeFrame"
- "Learn how to install package in Python in ManeFrame"
keypoints:
- "Python workflow"
- "ManeFrame"
---

## Create your own conda environment
- We encourage all users to create their own conda environment so that they can use any specific version of python with the packages of their choices
- Once conda env is created, package can be installed via **conda** or **pip**, depending on the type of env used
- Conda environment are managed using conda, which is available on ManeFrame's modules **python/2** or **python/3**
- Step to create conda environment using terminal:

```bash
# Request a compute node if you do not have one (here I request for a node with 6 cpus and 16gb ram, running interactively):
$ srun -p htc -N 1 -c 6 --mem=16G --pty $SHELL

# Load python module
$ module load python/3

# Create a conda environment using python 3.7 version (-y denotes yes for installation)
$ conda create -y -n myPenv python=3.7

# Activate the newly created environment
$ source activate myPenv

# Install your own packages using pip or conda
$ pip install pandas
$ conda install -y jupyter
# If you want the specific version:
$ pip install scipy==1.7.1

# Make your conda environment available in Jupyter Notebook (accessible via Open OnDemand[https://hpc.smu.edu/pun/sys/dashboard/])
$ python -m ipykernel install --user --name myPenv --display-name "My 1st conda env"

# Deactivate your conda env once done
$ source deactivate
```


Now you are ready with the python pipeline running on ManeFrame

## Prepare a simple script (skip if you already have one)
Here I create a simple python script with following information and named it **hello.py**

```python
import random,datetime
print(datetime.datetime.now())
print("hello from ManeFrame")
print(random.random())
```

## Running interactive Python while in a login node using srun
While it is not recommended to run any job in a login node, we encourage every user to run their own job in compute node.
If you are in a login node, you can run a job via this command:

```bash
$ srun -p htc --mem=6G python hello.py
```

## Running interactive Python from a compute node
First, request an interactive node:

```bash
$ srun -p htc --mem=6G --pty $SHELL
```

Then load python, activate the environment and run your script:

```bash
$ module load python/3
$ source activate myPenv
$ python hello.py
```

## Running non-interactive Python while in a login node using sbatch
Still in a login node, using **sbatch --wrap** to wrap a command in an sbatch script, then submitted to the queue to run in batch mode (non interactive)

```bash
$ sbatch -p htc --mem=6G --wrap "module load python/3; source activate myPenv; time python hello.py"
```

You will find the output in the same folder with the format of **slurm-$JobID.out**.


## Running non-interactive Python while in a login node via a batch script (most advance)
First create a batch script named _**myfirst_batch.sh**_

```bash
#!/bin/bash
#SBATCH -J python
#SBATCH -o python_%j.out
#SBATCH -p htc
#SBATCH --mem=6G

module purge
module load python/3

source activate myPenv
time python hello.py
```

Then, while in a login node, submit a batch script 

```bash
$ sbatch myfirst_batch.sh
```

You can see the output starting with ($Job_Name)_($JobID)

