---
layout: post
title: "Setting up Rethinking Few-shot 3D Point Cloud Semantic Segmentation."
---
# Intro
Bro let's try to reproduse results from this paper for fun?

# Body

Getting Repo:  
```
git clone https://github.com/ZhaochongAn/COSeg
cd COSeg 
```

I think python version between 3.8 - 3.10 for this repo
so:  
## Setting python up
Getting old python:
```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.10 python3.10-venv
```

Setting envoroment up:
```
python3.10 -m venv myenv 
source myenv/bin/activate
pip install --upgrade pip setuptools wheel

```
## Installing requirements
So if you do `pip install -r requirements.txt` it is obviosly just fails.  
 we need to sort requirements by opder of dependensies.

### sorting req
cvrazy it probably imposible to do, just by hand???



# Conclusion

---
Open issue for any comments.
