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



# OLD


Get code from [here](https://github.com/ashawkey/torch-ngp):
```
git clone --recursive https://github.com/ashawkey/torch-ngp.git
cd torch-ngp
```

## Installation

Install requirements:
add `- pip` as explisit dependency in `environment.yml`  
```
conda env create -f environment.yml
or
pip install -r requirements.txt
```
if conda install failed try pip.

set CUDA_HOME
```
ls /usr/local/ | grep cuda
export CUDA_HOME=/usr/local/cuda-X.X
```


## Get data
Download data [from here](https://www.dropbox.com/s/0bf6fl0ye2vz3vr/data.zip?dl=0)  
data taked form [this repo](https://github.com/albertpumarola/D-NeRF?tab=readme-ov-file)
 
## Test run
```
python main_dnerf.py ../data/dnerf/jumpingjacks --workspace trial_dnerf_jumpingjacks -O --bound 1.0 --scale 0.8 --dt_gamma 0

```

# Sourses
- [cuda 9.0 installation guidline for ubuntu 18.04 LTS](https://gist.github.com/Brainiarc7/470a57e5c9fc9ab9f9c4e042d5941a40)  

