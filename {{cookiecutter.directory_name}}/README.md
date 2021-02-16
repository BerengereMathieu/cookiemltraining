# cookiemltraining

Cookiecutter template for machine learning training projects. 

## Installation

### Virtualenv

1. create virtualenv `virtualenv venv`
2. activate virtualenv `source venv/bin/activate`
3. install basic requirements `pip install -r basic_requirements.txt`
4. install virtual env specific requirements `pip install -r additional_virtualenv_requirements`

### Pre-commit 

Pre-commit is installed with virtual env. You need to initialize it : 

`pre-commit install`

### Docker

1. Install docker : you can follow instruction [here](https://www.pugetsystems.com/labs/hpc/Workstation-Setup-for-Docker-with-the-New-NVIDIA-Container-Toolkit-nvidia-docker2-is-deprecated-1568/)
2. Build docker image : `docker build . -t autonomens/iasd_project:1.0`

**If you want use your NVIDIA GPU :**

First you need to install [nvidia-driver](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html)

Next you can check that everything is right for nvidia : `docker run --gpus all --rm nvidia/cuda nvidia-smi`

### Launch container

Run docker image :
    + to use CPU computing : `docker run -it --rm -v $PWD:/iasd_project -u root autonomens/iasd_project:1.0`
    + to use NVIDIA GPU computing : `docker run --gpus all -it --rm -v $PWD:/iasd_project -u root autonomens/iasd_project:1.0`
Your docker  use [tensorflow official docker](https://www.tensorflow.org/install/docker?hl=fr).
