FROM stand/docker_deeppavlov:cuda-9.0_jup

WORKDIR /base

RUN pip3 install jupyter

EXPOSE 8888

CMD jupyter notebook --ip 0.0.0.0 --no-browser --allow-root --NotebookApp.token=''