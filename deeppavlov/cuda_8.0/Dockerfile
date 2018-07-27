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