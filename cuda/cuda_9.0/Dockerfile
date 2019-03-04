# Copyright 2017 Neural Networks and Deep Learning lab, MIPT
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM nvidia/cuda:9.0-devel-ubuntu16.04

ENV PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
ENV LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

WORKDIR /base

# Install stand basic dependencies

RUN apt-get update
RUN apt-get -y install --only-upgrade bash
RUN apt-get -y install software-properties-common
RUN add-apt-repository -y ppa:ubuntu-toolchain-r/test
RUN apt-get update
RUN apt-get -y install locales && locale-gen en_US.UTF-8 && locale-gen ru_RU.UTF-8
RUN apt-get -y install git
RUN git config --global user.email "litinsky@ipavlov.ai"
RUN git config --global user.name "litinsky"
RUN apt-get -y install wget
RUN apt-get -y install tar
RUN apt-get -y install gcc-6 g++-6
RUN apt-get -y install build-essential libssl-dev zlib1g-dev libncurses5-dev libreadline-dev libgdbm-dev libdb5.3-dev libbz2-dev liblzma-dev libsqlite3-dev libffi-dev tcl-dev tk tk-dev
RUN wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tar.xz && \
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
