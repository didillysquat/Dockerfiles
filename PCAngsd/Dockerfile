################## BASE IMAGE #####################
FROM ubuntu:jammy-20220101 

################## METADATA #######################

LABEL base_image="ubuntu:jammy-20220101"
LABEL software="PCAngsd"
LABEL about.summary="Ubuntu 22.04 based image with PCAngsd installed; https://github.com/Rosemeis/pcangsd"

################## MAINTAINER ######################
MAINTAINER Benjamin C C Hume didillysquat@gmail.com

RUN apt-get update
# Required to prevent the interactive prompt preventing build
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections
RUN apt-get install -y git build-essential libcurl4-openssl-dev libz-dev libbz2-dev liblzma-dev python3 python3-distutils python3-pip python3-setuptools
RUN git clone https://github.com/Rosemeis/pcangsd.git
WORKDIR /pcangsd
# The install documentation says to use -users but this means the 
# modules are not available for users
RUN pip install -r requirements.txt
ENV PATH="$PATH:/root/.local/bin"
RUN python3 setup.py build_ext --inplace
RUN chmod -R +x . 
# Put a shebang at the top of the pcangsd.py so that it can be 
# executed directly
RUN sed -i '1s/^/#!\/usr\/bin\/env python3\n/' pcangsd.py
RUN ln -s /pcangsd/pcangsd.py /usr/bin/pcangsd.py
RUN ln -s /usr/bin/python3 /usr/bin/python
