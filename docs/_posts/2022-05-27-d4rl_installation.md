---
layout: post
title: "Seting up D4RL with conda on remote server"
---
# Seting up D4RL with conda on remote server
Machine: Ubuntu 20.04.3 LTS focal

## Install d4rl
``` shell
conda create --name offlineRL python=3.9
conda activate offlineRL
conda install pip
git clone https://github.com/rail-berkeley/d4rl.git
cd d4rl
pip install -e .
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
conda install -c anaconda networkx
pip install pygame
conda install -c conda-forge dotmap
```

## FLOW


## Check if libs exist
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
