################## BASE IMAGE #####################
FROM ubuntu:groovy 

################## METADATA #######################

LABEL base_image="ubuntu:groovy"
LABEL software="lcmlkin"
LABEL about.summary="Ubuntu 20.0.4 based image with lcmlkin installed"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com

RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    && rm -rf /var/lib/apt/lists/* 

RUN mkdir lcmlkin && cd lcmlkin && \
    git clone https://github.com/didillysquat/maximum-likelihood-relatedness-estimation.git && \
    cd maximum-likelihood-relatedness-estimation && make && \
    ln -s /lcmlkin/maximum-likelihood-relatedness-estimation/lcmlkin /bin/lcmlkin
