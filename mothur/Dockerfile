FROM ubuntu:groovy-20210225

MAINTAINER Benjamin Hume <didillysquat@gmail.com>

RUN apt-get update && apt-get -y install wget unzip && \
    wget https://github.com/mothur/mothur/releases/download/v.1.45.0/Mothur.Ubuntu_20.zip && \
    unzip Mothur.Ubuntu_20.zip && \
    rm Mothur.Ubuntu_20.zip && \
    rm -rf __MACOSX

#adds executables to the path
ENV PATH /mothur:$PATH
