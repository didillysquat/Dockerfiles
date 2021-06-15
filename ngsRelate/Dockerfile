################## BASE IMAGE #####################
FROM ubuntu:groovy 

################## METADATA #######################

LABEL base_image="ubuntu:groovy"
LABEL software="NgsRelate"
LABEL about.summary="Ubuntu 20.0.4 based image with NgsRelate installed; https://github.com/ANGSD/NgsRelate"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com

RUN apt-get update
RUN apt-get install -y git build-essential libcurl4-openssl-dev libz-dev libbz2-dev liblzma-dev
RUN git clone --recursive https://github.com/SAMtools/htslib && git clone https://github.com/ANGSD/ngsRelate
RUN cd htslib/ && make -j2
RUN cd ../ngsRelate && make HTSSRC=../htslib/
RUN ln -s /ngs_relate/ngsRelate/ngsRelate /usr/bin/ngsRelate
