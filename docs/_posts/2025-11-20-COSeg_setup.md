---
layout: post
title: "How to run: Rethinking Few-shot 3D Point Cloud Semantic Segmentation."
---
*My dream is, for each repo be like a cooking recipe:  
follow steps - get the dish.*

---
# Intro


Let's try to reproduse results from [this](https://arxiv.org/pdf/2403.00592) paper for fun?

I think python version between 3.8 - 3.10 for this repo
I tried python 3.8, 3.10 and 3.9 some packages SCREAMING that thay need <3.9 so 3.8 it is?


# Body

Getting Repo:  
```
git clone https://github.com/ZhaochongAn/COSeg
cd COSeg 
```

## Setting python up
Getting old python:
```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.10 python3.10-venv
sudo apt install python3.9 python3.9-venv
sudo apt install python3.8 python3.8-venv
sudo apt install python3.7 python3.7-venv
sudo apt install python3.6 python3.6-venv
```

Setting envoroment up:
```
python3.8 -m venv myenv
python3.7 -m venv myenv

source myenv/bin/activate
pip install --upgrade pip setuptools wheel

```
## Installing requirements
So if you do `
pip install -r requirements.txt
` it is obviosly just fails.
`torch_scatter` convinced that `torch` doesn't exist.

Ok, let's try to install all step by step:
```
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113
pip install torch_points3d==1.3.0
pip install torch-scatter==2.1.1
pip install torch-points-kernels==0.6.10
pip install torch-geometric==1.7.2
pip install timm==0.9.2
pip install tensorboardX==2.6
pip install numpy==1.20.3
```

Trying to installing things separatly:
```
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 \
    --extra-index-url https://download.pytorch.org/whl/cu113

pip install \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/pyg_lib-0.2.0%2Bpt111cu113-cp39-cp39-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_cluster-1.6.0-cp39-cp39-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_scatter-2.0.9-cp39-cp39-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_sparse-0.6.13-cp39-cp39-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_spline_conv-1.2.1-cp39-cp39-linux_x86_64.whl 

pip install \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/pyg_lib-0.2.0%2Bpt111cu113-cp37-cp37m-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_cluster-1.6.0-cp37-cp37m-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_scatter-2.0.9-cp37-cp37m-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_sparse-0.6.13-cp37-cp37m-linux_x86_64.whl \
https://data.pyg.org/whl/torch-1.11.0%2Bcu113/torch_spline_conv-1.2.1-cp37-cp37m-linux_x86_64.whl 

#pip install numpy==1.21.6 --force-reinstall
pip install "numpy<1.24" --force-reinstall
```

## Actually running Models or smth?
```
```

# Conclusion
Well this is impossible I giveup for now=(

---
Open issue for any comments.
