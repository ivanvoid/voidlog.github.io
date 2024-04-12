---
layout: post
title: "Running D-Nerf"
---
# Running D-Nerf

## Source code borrowing
In order to run code, we need to get code.

Get code from [here](https://github.com/ashawkey/torch-ngp):
```
git clone --recursive https://github.com/ashawkey/torch-ngp.git
cd torch-ngp
```

Install requirements:
add `- pip` as explisit dependency in `environment.yml`  
```
conda env create -f environment.yml
or
pip install -r requirements.txt
```
if conda install failed try pip.


## Get data
Download data [from here](https://www.dropbox.com/s/0bf6fl0ye2vz3vr/data.zip?dl=0)  
data taked form [this repo](https://github.com/albertpumarola/D-NeRF?tab=readme-ov-file)
 
## Test run
```
python main_dnerf.py ../data/dnerf/jumpingjacks --workspace trial_dnerf_jumpingjacks -O --bound 1.0 --scale 0.8 --dt_gamma 0

```

# Sourses
- [cuda 9.0 installation guidline for ubuntu 18.04 LTS](https://gist.github.com/Brainiarc7/470a57e5c9fc9ab9f9c4e042d5941a40)  

