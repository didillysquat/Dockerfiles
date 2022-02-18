################## BASE IMAGE #####################
FROM ubuntu:jammy-20220101 

################## METADATA #######################

LABEL base_image="ubuntu:jammy-20220101"
LABEL software="Flink https://bitbucket.org/wegmannlab/flink/wiki/Home"
LABEL about.summary="Ubuntu 22.04 based image with Flink installed" 

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com
RUN apt-get update
RUN apt-get install -y wget build-essential libz-dev git zip liblapack-dev libblas-dev libboost-dev libarmadillo-dev
ADD flink /flink
RUN cd flink && make clean && make
RUN ln -s /flink/flink /usr/bin/flink
ADD atlas /atlas
RUN cd atlas && make
RUN ln -s /atlas/atlas /usr/bin/atlas
