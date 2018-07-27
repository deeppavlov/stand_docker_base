# Base Dockerfile for the GPU based stand models

## Installation and build

1. Install Docker according the instructions:
   
   https://docs.docker.com/install/linux/docker-ce/ubuntu/
   
2. Install nVIDIA Docker according the instructions:

   https://github.com/NVIDIA/nvidia-docker
   
3. Clone the repo and `cd` to project root:
    ```
    git clone https://github.com/deepmipt/stand_docker_base.git
    cd stand_docker_base
    ```
4. Build base stand Docker images for each CUDA versions:
    ```
    sudo docker build -t stand/docker_cuda:8.0 cuda/cuda_8.0/
    sudo docker build -t stand/docker_deeppavlov:cuda-8.0 deeppavlov/cuda_8.0/

    sudo docker build -t stand/docker_cuda:9.0 cuda/cuda_9.0/
    sudo docker build -t stand/docker_deeppavlov:cuda-9.0 deeppavlov/cuda_9.0/
    
    sudo docker build -t stand/docker_cuda:9.1 cuda/cuda_9.1/
    sudo docker build -t stand/docker_deeppavlov:cuda-9.1 deeppavlov/cuda_9.1/
    ```