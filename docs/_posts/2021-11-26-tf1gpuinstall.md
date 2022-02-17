---
layout: post
title: "How to install Tensorflow 1.0.1 on Ubuntu 18 with CUDA 8.0"
---
# How to install Tensorflow 1.0.1 on Ubuntu 18 with CUDA 8.0
  
  
## Steps to follow to remove all:
- `sudo apt-get remove \-\-purge '^nvidia-.*'`
- `sudo apt-get remove \-\-purge '^libnvidia-.*'`
- `sudo apt-get remove \-\-purge '^cuda-.*'`
- `sudo rm -rf /usr/local/cuda*`
- `sudo apt update`
- `sudo apt upgrade`
- `sudo apt autoremove`

## Steps to install drivers
- `sudo ubuntu-drivers autoinstall`
- `nvidia-smi`

or
 
- $ `nvidia-detector`
- `sudo apt install nvidia-driver-[your version]`

## Step to install cuda-toolkit
- go to 'developer.nvidia.com/cuda-toolkit-archive'
- select 'CUDA Toolkit 8.0 GA2'
- Next follow: Linux/x86/_64/Ubuntu/runfile(local) and download this file to your linux machine
- Install it: `$ sudo sh cuda_8....linux.run`, no drivers, no samples  
    - accept
    - y
    - n
    - y
    - (/usr/local/cuda-8.0)
    - samplels: n
    - symbolic link: y


## After that everything should work, you can check it by typing:
- `conda create --name tf1-gpu-py27 python=2.7`
- `conda activate tf1-gpu-py27`
- `conda install pip`
- `./miniconda/envs/tf1-gpu-py27/bin/pip install tensorflow-gpu==1.0.1`
- `./miniconda/envs/tf1-gpu-py27/bin/python2`
- `alias python-2=./miniconda/envs/tf1-gpu-py27/bin/python2`
- `python-2`
    - `>>> import tensorflow as tf`
    - `>>> tf.__version__`
    '1.0.1'
    - `>>> tf.test.is_gpu_available()`
<!-- - `cuda cad output`; -->
