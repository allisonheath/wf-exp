FROM phusion/baseimage:0.9.17
MAINTAINER Allison Heath <aheath@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
ENV HOME /root

# Packages needed for STAR
RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y g++
RUN apt-get install -y make
RUN apt-get install -y zlib1g-dev

# Clean up any files used by apt-get
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Change our working directory to /root
WORKDIR /root

ENV STAR_VERSION 2.4.2a

RUN curl -L -O https://github.com/alexdobin/STAR/archive/STAR_$STAR_VERSION.tar.gz
RUN tar zxvf STAR_$STAR_VERSION.tar.gz

WORKDIR /root/STAR-STAR_$STAR_VERSION/source
RUN make STAR
RUN mv STAR /usr/local/bin
