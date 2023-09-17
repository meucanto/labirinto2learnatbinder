# Setup of lab2learn
Lab environment for Jupyter applications.


## Table of contents

<!--
    The table of contents is automatically generated using the following sublime package:
    https://packagecontrol.io/packages/MarkdownTOC 

    Do not remove the html comments below
-->

<!-- MarkdownTOC autolink=true -->

- [Running these labs](#running-this-lab)
  - [Launching via Cloud Services](#launching-via-cloud-services)
    - [Via MyBinder.org \(instance of the project jupyterhub/binderhub\)](#via-mybinderorg-instance-of-the-project-jupyterhubbinderhub)
    - [Via Google Colaboratory](#via-google-colaboratory)
  - [Launching Locally via Docker](#launching-locally-via-docker)
    - [DockerHub Image](#dockerhub-image)
    - [Using repo2docker](#using-repo2docker)
- [SQL Labs](sql/)

<!-- /MarkdownTOC -->

## Running these labs

Examples and exercises in this lab are presented as [Jupyter Notebooks](http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html). 
Get started with this lab simply by cloning this repository within your own Jupyter environment or by launching an environment in the cloud services listed below.

### Launching via Cloud Services

#### Via [MyBinder.org](http://mybinder.org/) (instance of the project jupyterhub/[binderhub](https://github.com/jupyterhub/binderhub))


  * Jupyter Lab:   
  [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/meucanto/labirinto2learnatbinder/HEAD?urlpath=lab)
  

  * Jupyter:     
  [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/meucanto/labirinto2learnatbinder/HEAD?urlpath=lab)



#### Via [Google Colaboratory](https://colab.research.google.com)

  * Jupyter Notebook:   
  [![Binder](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/github/santanche/lab2learn)

### Launching Locally via Docker

You may also launch this lab on your own environment using Docker, either using our own image or building one with repo2docker. Instructions on how to install Docker can be found [here](https://docs.docker.com/install/)


#### DockerHub Image

Launch [our own Docker image](https://hub.docker.com/r/santanche/lab2learn/) with the command:  
```bash
docker run -it -p 8888:8888 santanche/lab2learn
``` 

Alternatively, you can map you local home folder into the container:

```bash
docker run -it -v ~:/home/jovyan -p 8888:8888 santanche/lab2learn
``` 

Access the Jupyter/Jupyter Lab at [http://0.0.0.0:8888](http://0.0.0.0:8888). 

The *Dockerfile* used to build the image can be found [here](https://github.com/santanche/lab2learn/tree/master/resources/docker/image).


#### Using [repo2docker](https://github.com/jupyter/repo2docker)

You can run a containerized instance of Jupyter/Jupyter Lab via the [repo2docker](https://github.com/jupyter/repo2docker) tool. Repo2docker will clone this repository, build a docker image with all internal requirements, and launch a Jupyter/JupyterLab instance. Try:

```bash
repo2docker -p 8888:8888 https://github.com/santanche/lab2learn  jupyter-lab --ip 0.0.0.0 --NotebookApp.token=''
```

Alternatively, you can map you local home folder into the container:
```bash
repo2docker -p 8888:8888 -v ~:`pwd`  https://github.com/santanche/lab2learn  jupyter-lab --ip 0.0.0.0 --NotebookApp.token=''
```

Access the Jupyter Lab server by going to [http://0.0.0.0:8888/lab](http://0.0.0.0:8888). 
