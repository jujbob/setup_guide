# [Install Anaconda]

## MacOS, Linux
 ```
   wget https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh
   sh Anaconda3-5.2.0-Linux-x86_64.sh

   conda search python
   conda create -n Utagger python=3.6 anaconda
   conda activate Utagger
 ```

# [Install CUDA]
 * Reference: https://gist.github.com/zhanwenchen/e520767a409325d9961072f666815bb8
 * Setup CUDA 9.0
```
    cd $HOME
    mkdir cuda_installer
    wget https://developer.nvidia.com/compute/cuda/9.0/Prod/local_installers/cuda_9.0.176_384.81_linux-run
    chmod +x cuda_9.0.176_384.81_linux-run
    ./cuda_9.0.176_384.81_linux-run --extract=$HOME/cuda_installer
    sudo ./cuda-linux.9.0.176-22781540.run
    
```
 * Setup CuDNN
```    
    Dowonload CuDnn package from https://developer.nvidia.com/rdp/cudnn-download
    sftp $SERVERHOST
    put cudnn-9.0-linux-x64-v7.tgz
    exit
    
    cd /usr/local
    sudo tar -xvzf cudnn-9.0-linux-x64-v7.tgz
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


# [bashes and env in Ubuntu]
Bash는 쉘과 스크립트 언어의 성격을 모두 가지고 있습니다. 스크립트로 사용할 때, 쉘 프로그래밍 혹은 쉘 스크립팅이라고 합니다. 프로그래밍 요소가 있기 때문에 위와 같이 변수를 관리하는 명령이 있습니다. 환경 변수와 쉘 변수는 다른 데, 다른 언어에서는 쉽게 구분이 가능한 반면에, 쉘 프로그래밍을 하다 보면 이 두 가지의 사용 용법이 비슷하여 동일한 것으로 오해할 수 있습니다.
유닉스는 "Small is beautiful"이라는 유닉스의 철학에 맞게 작은 프로그램들의 집합으로 구성된 시스템이며, 리눅스는 이를 모방하여 만들어, 별거아닌 것 같은 기능들도 모두 작은 프로그램으로 제공하며, 이러한 명령어들을 이용하여 쉘 프로그래밍을 할 수 있습니다.
출처: https://hashcode.co.kr/questions/1893/%EB%A6%AC%EB%88%85%EC%8A%A4-%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95%ED%95%A0-%EB%95%8C-env-set-export-declare
리눅스에서 가장 많이 사용하는 Bash(혹은 sh)의 빌틴 명령어들입니다. 각 명령어마다 쓰임새가 조금씩 다릅니다.

*env : 환경변수를 보여주거나, 설정 혹은 삭제 하는 명령입니다. http://ss64.com/bash/env.html

$ env
현재 세션에 정의된 환경 변수들을 화면에 출력합니다.

$ env NAME=VALUE 
NAME이라는 환경변수에 VALUE라는 값을 지정합니다.

$ env -u NAME
NAME 환경변수를 삭제합니다.

*set : Bash의 쉘 변수를 관리하는 명령어입니다. http://ss64.com/bash/set.html

set NAME=VALUE 
# Bash에서는 다음과 같이 생략이 가능합니다.
NAME=VALUE
쉘 변수는 Bash라는 쉘 스크립트 언어에서 사용하는 변수이고, 환경 변수는 운영체제에서 사용하는 변수(예: PATH)입니다.
해제하는 방법은 unset 명령어를 사용합니다.

*export: 쉘 변수를 환경 변수로 변경해주는 명령입니다.

NAME=VALUE
export NAME
위는 set과 export를 사용하여 다음 명령과 동일한 결과를 가져옵니다.

env NAME=VALUE

*declare: 이는 쉘 변수의 타입을 지정하는 명령입니다. https://wiki.kldp.org/HOWTO/html/Adv-Bash-Scr-HOWTO/declareref.html

읽기전용, 정수, 배열, 함수 등으로 쉘 변수의 성격을 선언할 때 사용합니다.
