---
layout: post
title: "Running D-Nerf"
---
# Running D-Nerf

## Source code borrowing
In order to run code, we need to get code.

[D-NeRF](https://github.com/albertpumarola/D-NeRF)

## Installation
```
cd D-NeRF
conda create -n dnerf python=3.6
conda activate dnerf
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
cd torchsearchsorted
pip install .
cd ..
```
if opencv fails: `pip install --no-use-pep517 opencv-python`

for CUDA-12:
`conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia`


## FIXING CODE
FIX searchsorted  
https://pytorch.org/docs/stable/generated/torch.searchsorted.html


## RUNNING
```
conda activate dnerf
python run_dnerf.py --config configs/mutant.txt
```

Running tensorboard:
```
pip3 install tensorboard
~/miniconda3/envs/dnerf/bin/tensorboard --logdir=./logs
```

OOM errors:  
Set chunk in ./config/name.txt to lower values.   
```
chunk = 1024
```

# Iteration on D-NeRF
So [this dude](https://github.com/ashawkey/torch-ngp) already put hash into d-nerf.  
[Fast NeRF](https://github.com/mrcabellom/fastNerf) speeding up 200x fps.

## Adding Hash encoding.


## Adding split networks



# Sourses
- [cuda 9.0 installation guidline for ubuntu 18.04 LTS](https://gist.github.com/Brainiarc7/470a57e5c9fc9ab9f9c4e042d5941a40)  

# Research Notes
TODO IMPORTANT:
- Write experiments section
- Write Discussion section
- Write conclusion section
- Get metrics: MSE, PSNR, etc 
- copy, change things, check metrics AGAIN.
- repeat till metrics will be better.
- profit?
- Generate experements table 1. Quality of predictions.
- Generate experements table 2. Speed of training
- Generate experements table 3. Speed of inference?
  
TODO SECONDARY:
- Plot images, prediction results.
- Replace position with p, and final vector with x.

DONE:
- Render intro graph and images. [+++]
- Run original dnerf in one line on different datasets. [+++]
- Refine problem definition. [+++]
- Write Method. [+++]
- Describe Implementation details [+++]    


