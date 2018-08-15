FROM stand/docker_cuda:9.0

WORKDIR /base

RUN apt-get update && \
    pip install pip==10.0.1 && \
    git clone https://github.com/deepmipt/DeepPavlov.git && \
    cd DeepPavlov && \
    git checkout dev && \
    python3.6 setup.py develop && \
    printf "import nltk\nnltk.download('punkt')" | python3.6 && \
    printf "import nltk\nnltk.download('stopwords')" | python3.6 && \
    printf "import nltk\nnltk.download('perluniprops')" | python3.6 && \
    printf "import nltk\nnltk.download('nonbreaking_prefixes')" | python3.6