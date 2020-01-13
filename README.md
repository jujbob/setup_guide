# [Install Anaconda]

## MacOS, Linux
 ```
   wget https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh
   sh Anaconda3-5.2.0-Linux-x86_64.sh

   conda search python
   conda create -n Utagger python=3.6 anaconda
   conda activate Utagger
 ```

# [Install Pytorch]

### Cuda version check!! :
nvcc --version

### An example of installing pytorch with CUDA 9.1
conda install pytorch=0.4.0 cuda91 -c soumith

### Pytorch without CUDA
conda install pytorch=0.4.0 -c soumith


# [Install python pacakages]

## Install python packages (when you have requriements.txt)
pip install -r requirements.txt

## Install individual python packages
pip install -r requirements.txt
conda install ftfy


# [Install git and clone source codes]

## Install github package
pip install git
## Clone the source using git
git clone https://naacl@bitbucket.org/naacl/tagger.git

# [Install git and clone source codes]

## A way of execution python code with GPU in a terminal 
CUDA_VISIBLE_DEVICES=0 python test1.py  # Uses GPU 0.
CUDA_VISIBLE_DEVICES=1 python test2.py  # Uses GPU 1.
CUDA_VISIBLE_DEVICES=2,3 python test3.py  # Uses GPUs 2 and 3.

## A way of execution python with GPU in python code
 ```
  import os
  os.environ["CUDA_DEVICE_ORDER"]="PCI_BUS_ID"   
  os.environ["CUDA_VISIBLE_DEVICES"]="0"
 ```

# [Jupyter notebook setup]
https://surpassing.tistory.com/824

