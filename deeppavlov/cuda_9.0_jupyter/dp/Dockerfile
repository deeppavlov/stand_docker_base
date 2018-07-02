FROM stand/docker_cuda:9.0

WORKDIR /base

RUN apt-get update && \
    pip install pip==10.0.1 && \
    git clone https://github.com/deepmipt/DeepPavlov.git && \
    cd DeepPavlov && \
    python3.6 setup.py develop && \
    python3.6 -m spacy download en && \
    printf "import nltk\nnltk.download('punkt')" | python3.6