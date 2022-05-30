---
layout: post
title: "Seting up D4RL with conda on Ubuntu"
---
# Seting up D4RL with conda on Ubuntu
Machine: Ubuntu 20.04.3 LTS focal

## Install D4RL
``` shell
conda create --name offlineRL python=3.8
conda activate offlineRL
conda install pip
git clone https://github.com/rail-berkeley/d4rl.git
cd d4rl
pip install -e .
cd ..
```

## Install MuJoCo   
``` shell
wget https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz
tar -xvzf mujoco210-linux-x86_64.tar.gz
mkdir ~/.mujoco
mv mujoco210 ~/.mujoco/
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/ivan/.mujoco/mujoco210/bin' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib/nvidia' >> ~/.bashrc
. ~/.bashrc
```

## Install CLARA 
```
mkdir CARLA
cd CARLA
wget https://carla-releases.s3.eu-west-3.amazonaws.com/Linux/CARLA_0.9.8.tar.gz
wget https://carla-releases.s3.eu-west-3.amazonaws.com/Linux/AdditionalMaps_0.9.8.tar.gz
tar -xvzf CARLA_0.9.8.tar.gz
tar -xvzf AdditionalMaps_0.9.8.tar.gz
echo 'export PYTHONPATH=$PYTHONPATH:/home/CARLA_0.9.8/PythonAPI' >> ~/.bashrc
echo 'export PYTHONPATH=$PYTHONPATH:/home/CARLA_0.9.8/PythonAPI/carla' >> ~/.bashrc
echo 'export PYTHONPATH=$PYTHONPATH:/home/CARLA_0.9.8/PythonAPI/carla/dist/carla-0.9.8-py3.5-linux-x86_64.egg' >> ~/.bashrc
conda activate offlineRL
conda install -c anaconda networkx
pip install pygame
conda install -c conda-forge dotmap
cd ..
```

## FLOW
```
git clone https://github.com/flow-project/flow.git
cd flow
```
Error without it: *redis 2.10.6 is installed but redis>=3.3.2 is required by {'ray'}*  
I repleace the "redis~=2.10.6" by "redis" in enviroment.yml and requirements.txt.

```
conda env create -f environment.yml
conda activate flow
python setup.py develop
```
Next, we install the SUMO.
```
sudo apt-get install sumo sumo-tools sumo-doc
```
Checking 
```
which sumo
sumo --version
sumo-gui
```
**PS: It still does't work**


## Check if libs exist(optional)
I got errors, so I needed to install those.
``` shell
sudo apt install libx11-dev
sudo apt install libglew-dev
sudo apt-get install patchelf
sudo apt install libosmesa6-dev
```

## Run test script 
``` shell
conda activate offlineRL
```
Write to file test_env.py:
``` python
import gym
import d4rl # Import required to register environments
```
run:
```
python test.py
```


All matireals from:
- [D4RL](https://github.com/rail-berkeley/d4rl)
- [MuJoCo-py](https://github.com/openai/mujoco-py)
- [CARLA-Setup](https://github.com/rail-berkeley/d4rl/wiki/CARLA-Setup)
- [FLOW-Setup](https://flow.readthedocs.io/en/latest/flow_setup.html)
