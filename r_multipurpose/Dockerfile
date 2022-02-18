################## BASE IMAGE #####################
FROM ubuntu:impish-20220128 

################## METADATA #######################

LABEL base_image="ubuntu:impish-20220128"
LABEL software="r-base"
LABEL about.summary="Ubuntu 21.10 based image with R installed and the packages listed below"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com


RUN apt-get update
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections
RUN apt install -y --no-install-recommends software-properties-common dirmngr wget build-essential
RUN wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc
RUN add-apt-repository -y "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"
RUN apt install -y --no-install-recommends r-base r-base-dev
RUN echo "deb https://cloud.r-project.org/bin/linux/ubuntu impish-cran40/" >> /etc/apt/sources.list
RUN Rscript --vanilla -e 'install.packages(c("stringr", "ggplot2", "tidyr", "gridExtra", "dplyr", "qqman"), repos="http://cran.us.r-project.org" )'
