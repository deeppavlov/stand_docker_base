FROM nvidia/cuda:9.0-devel-ubuntu16.04

WORKDIR /base

# Install stand basic dependencies

RUN apt-get update && \
    apt-get -y install --only-upgrade bash && \
    apt-get -y install software-properties-common && \
    add-apt-repository -y ppa:ubuntu-toolchain-r/test && \
    apt-get update && \
    apt-get -y install locales && locale-gen en_US.UTF-8 && locale-gen ru_RU.UTF-8 && \
    apt-get -y install git && \
    git config --global user.email "litinsky@ipavlov.ai" && \
    git config --global user.name "litinsky" && \
    apt-get -y install wget && \
    apt-get -y install tar && \
    apt-get -y install gcc-6 g++-6 && \
    apt-get -y install build-essential libssl-dev zlib1g-dev libncurses5-dev libreadline-dev libgdbm-dev libdb5.3-dev libbz2-dev liblzma-dev libsqlite3-dev libffi-dev tcl-dev tk tk-dev && \
    wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tar.xz && \
    tar xf Python-3.6.5.tar.xz && \
    cd Python-3.6.5 && \
    ./configure && \
    make altinstall

RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3.6 get-pip.py

ENV LANG='en_US.UTF-8' LANGUAGE='en_US.UTF-8' LC_ALL='en_US.UTF-8'


# Install cuDNN

# cuDNN7

ENV CUDNN_VERSION 7.1.4.18
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

RUN apt-get update && apt-get install -y --no-install-recommends \
            libcudnn7=$CUDNN_VERSION-1+cuda9.0 \
            libcudnn7-dev=$CUDNN_VERSION-1+cuda9.0 && \
    rm -rf /var/lib/apt/lists/*
