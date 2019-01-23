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

FROM stand/docker_cuda:8.0

WORKDIR /base

RUN apt-get update && \
    pip install pip==10.0.1 && \
    git clone https://github.com/deepmipt/DeepPavlov.git && \
    cd DeepPavlov && \
    git checkout a094badb4826d40480504889c3038272d6c79980 && \
    python3.6 setup.py develop && \
    python3.6 -m spacy download en && \
    printf "import nltk\nnltk.download('punkt')" | python3.6 && \
    printf "import nltk\nnltk.download('stopwords')" | python3.6 && \
    printf "import nltk\nnltk.download('perluniprops')" | python3.6 && \
    printf "import nltk\nnltk.download('nonbreaking_prefixes')" | python3.6