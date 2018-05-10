FROM stand/docker_cuda

WORKDIR /base

RUN apt-get update && \
    pip install pip==10.0.1 && \
    git clone https://github.com/deepmipt/DeepPavlov.git && \
    cd DeepPavlov && \
    git checkout dev && \
    python3.6 setup.py develop && \
    pip install http://lnsigo.mipt.ru/export/en_core_web_sm-2.0.0.tar.gz && \
    python3.6 -m spacy link en_core_web_sm en --force && \
    printf "import nltk\nnltk.download('punkt')" | python3.6