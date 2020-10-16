# Dockerfile for building base R image
# ARG syntax https://docs.docker.com/engine/reference/builder/#arg
# ENV syntax https://docs.docker.com/engine/reference/builder/#env
# FROM syntax https://docs.docker.com/engine/reference/builder/#from
# LABEL syntax https://docs.docker.com/engine/reference/builder/#label
# RUN syntax https://docs.docker.com/engine/reference/builder/#run
# WORKDIR syntax https://docs.docker.com/engine/reference/builder/#workdir


# Setting the OS 
# See available OS https://hub.docker.com/search?q=&type=image&category=base
FROM ubuntu:18.04


# LABEL replaced the MAINTAINER command

LABEL maintainer="Rami Krispin <rami.krispin@gmail.com>"

# Setting the R version
ENV R_VERSION_MAJOR=4
ENV R_VERSION_MINOR=0
ENV R_VERSION_PATCH=0
ENV CONFIGURE_OPTIONS="--with-cairo --with-jpeglib --enable-R-shlib --with-blas --with-lapack"
ENV RENV_VERSION 0.9.3

# Installing tzdata

ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=UTC

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-utils\
    gfortran \
    git \
    g++ \
    libreadline-dev \
    libx11-dev \
    libxt-dev \
    libpng-dev \
    libjpeg-dev \
    libcairo2-dev \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    libudunits2-dev \
    libgdal-dev \
    libbz2-dev \
    libzstd-dev \
    liblzma-dev \
    libpcre2-dev \
    locales \
    openjdk-8-jdk \
    screen \
    texinfo \
    texlive \
    texlive-fonts-extra \
    vim \
    wget \
    xvfb \
    tzdata \
    sudo\
&& rm -rf /var/lib/apt/lists/*


# Install R

RUN wget https://cran.rstudio.com/src/base/R-${R_VERSION_MAJOR}/R-${R_VERSION_MAJOR}.${R_VERSION_MINOR}.${R_VERSION_PATCH}.tar.gz && \
    tar zxvf R-${R_VERSION_MAJOR}.${R_VERSION_MINOR}.${R_VERSION_PATCH}.tar.gz && \
    rm R-${R_VERSION_MAJOR}.${R_VERSION_MINOR}.${R_VERSION_PATCH}.tar.gz


WORKDIR /R-${R_VERSION_MAJOR}.${R_VERSION_MINOR}.${R_VERSION_PATCH}

RUN ./configure ${CONFIGURE_OPTIONS} && \
    make && \
    make install

# Updating the git version
# Github Actions required version 2.18 and above
RUN apt-get update && \
      apt-get -y install sudo

RUN sudo apt-get install software-properties-common -y
RUN sudo add-apt-repository ppa:git-core/ppa && \
	sudo apt-get update -y && \
	sudo apt-get install git -y

ENTRYPOINT ["sh", "-c"]

CMD ["R --no-save"]
