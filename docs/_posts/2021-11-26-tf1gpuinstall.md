---
layout: post
title: "How to install Tensorflow 1.0.1 on Ubuntu 18 with CUDA 8.0"
---
# How to install Tensorflow 1.0.1 on Ubuntu 18 with CUDA 8.0
  
Steps to follow:  
- `$ conda create --name tf1-gpu-py27 python=2.7 tensorflow-gpu==1.0.1`
- `$ conda activate tf1-gpu-py27`
- `$ sudo apt install nvidia-drivar-495`
  - You can check what drivers you need by running `$ nvidia-detector`
- `$ sudo apt install nvidia-cuda-toolkit`
- go to 'developer.nvidia.com/cuda-toolkit-archive'
- select 'CUDA Toolkit 8.0 GA2'
- Next follow: Linux/x86/_64/Ubuntu/runfile(local) and download this file to your linux machine
- Install it: `$ sudo sh cuda_8....linux.run`, no drivers, no samples  
  
After that everything should work, you can check it by typing:
- `$ python`
- `>> import tensorflow as tf`
- `>> tf.__version__`
