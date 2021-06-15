################## BASE IMAGE #####################
FROM ubuntu:groovy 

################## METADATA #######################

LABEL base_image="ubuntu:groovy"
LABEL software="read"
LABEL about.summary="Ubuntu 20.0.4 based image with read installed; https://bitbucket.org/tguenther/read/src/master/README.md"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get -y install littler python2.7 git
RUN git clone https://tguenther@bitbucket.org/tguenther/read.git
RUN ln -s /usr/bin/python2.7 /usr/bin/python && ln -s /usr/bin/python2.7 /usr/bin/python2 && ln -s /read/READ.py /usr/local/bin/READ.py && ln -s /read/READscript.R /usr/local/bin/READscript.R
RUN sed -i 's/READscript.R/\/usr\/local\/bin\/READscript.R/g' /read/READ.py 
WORKDIR /read
