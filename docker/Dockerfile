FROM jupyter/scipy-notebook

USER root

RUN git clone https://github.com/meucanto/labirinto2learnatbinder

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install $(grep -vE "^\s*#" ./labirinto2learnatbinder/binder/apt.txt  | tr "\n" " ") -y && \
    apt-get autoclean  -y && \
    apt-get autoremove -y 

# nodejs 10
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt-get install -y nodejs

RUN  chown -R ${NB_UID} ${HOME} && rm work -R

# moving to notebook user
USER ${NB_USER}


RUN pip install -r ./labirinto2learnatbinder/binder/requirements.txt

RUN chmod +x ./labirinto2learnatbinder/binder/postBuild && \
    sh       ./labirinto2learnatbinder/binder/postBuild


ENV LANG=C.UTF-8

EXPOSE 8888



CMD jupyter-lab --ip=0.0.0.0 --port=8888 --no-browser --notebook-dir=${HOME} --allow-root --NotebookApp.token=''