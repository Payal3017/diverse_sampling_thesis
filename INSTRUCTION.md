# Instruction

## Install all dependencies and create env

- Use python 3.9

- If you have anaconda then create environemnt using conda

```bash
# To create conda environment run below command
conda create -n "diverse" python=3.9

# activate conda environemnt
conda activate diverse
```
+ if not create using local python installation by installing python 3.9 version

+ then create environment using below command
```bash
python -m venv venv

# activate the environment using below command
# in powershell
./venv/Scripts/Activate.ps1

# in unix system (macos, linux)
. ./venv/bin/activate
```

+ after then check if correct version 

```bash
# verify python version if it 3.9 or not 
python --version

# install requirements for project
pip install -r requirements.txt

# install extra dependencies
pip install torch==1.10.0+cu113 torchvision==0.11.1+cu113 --index-url https://download.pytorch.org/whl/cu113

```

## To Train Chico model 

open `./chico/main_teacher.ipynb` and run all the block step by step in jupyter notebook


## Evaluatation


+ evaluate on Chico:

  `python main.py --exp_name=chico_t2 --is_load=1 --model_path=ckpt/pretrained/chico_t2.pth`



## Calculate perceptual scores (FID and ACC)

+ For Human3.6M:

  `python main_classifier.py --exp_name=chico_t2`



## Train

- train CVAE on chico:

   `python main.py --exp_name=chico_t1 --is_train=1`

- train DiverseSampling on chico:

  `python main.py --exp_name=chico_t2 --is_train=1`

