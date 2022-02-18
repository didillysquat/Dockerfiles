################## BASE IMAGE #####################
FROM ubuntu:jammy-20220101 

################## METADATA #######################

LABEL base_image="ubuntu:jammy-20220101"
LABEL software="bedtools v2.30.0 and preseq v3.1.2"
LABEL about.summary="Ubuntu 22.04 based image with bedtools and preseq installed so that a bam can be converted to bed file and used as input to preseq"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com
RUN apt-get update
RUN apt-get install -y wget build-essential libz-dev
RUN wget https://github.com/arq5x/bedtools2/releases/download/v2.30.0/bedtools.static.binary
RUN mv bedtools.static.binary bedtools
RUN chmod a+x bedtools
RUN mv bedtools /usr/bin
RUN wget https://github.com/smithlabcode/preseq/releases/download/v3.1.2/preseq-3.1.2.tar.gz
RUN tar -zxvf preseq-3.1.2.tar.gz
RUN cd preseq-3.1.2 && ./configure && make && make install
