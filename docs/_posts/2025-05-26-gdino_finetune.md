---
layout: post
title: "How to Finetune Grounding DINO"
---
# Overview  
Repo:   

https://github.com/ivanvoid/Grounding-Dino-FineTuning

# Refs
- https://github.com/open-mmlab/mmdetection/blob/dev-3.x/configs/grounding_dino/README.md
- https://github.com/Asad-Ismail/Grounding-Dino-FineTuning


(dino) ivan@hucenrotia-ai:~/Grounding-Dino-FineTuning$ /home/ivan/dino/bin/python -m pip install -q -e .


# Old Nodes
pip install -e .

python3 -m venv gdinoenv
activate gdinoenv/bin/activate
gdinoenv/bin/python -m pip install -r requirements.txt
echo 'export CUDA_HOME=/usr/local/cuda-12.6' >> ~/.bashrc
/home/ivan/gdinoenv/bin/python -m pip install -e .
/home/ivan/gdinoenv/bin/python train.py


CUDA 12.8
ivan@hucenrotia-ai:~/Grounding-Dino-FineTuning/configs$ ls /usr/local/ 
bin  cuda  cuda-12  cuda-12.6  etc  games  include  lib  man  sbin  share  src 

https://stackoverflow.com/questions/78058520/nameerror-c-is-not-defined


base_model.model.transformer.decoder.bbox_embed.0.layers.2.modules_to_save.default.weight













