FROM ubuntu:18.04

ARG DEBIAN_FORNTEND=noninteractive

RUN apt update && apt install -y software-properties-common \
    zlib1g-dev \
    libxml2-dev \
    libxt-dev \
    libcairo2-dev \
    libglpk-dev \
    libgmp3-dev \
    libmpfr-dev \
    libcurl4-gnutls-dev \
    libmysqlclient-dev \
    libjpeg-dev

RUN apt-key adv --keyserver keyserver.ubuntu.com \
    --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9 && \
    add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/' && \
    apt update && \
    apt install -y r-base

ADD ./metar_deps /home/metar

RUN R -e "devtools::install_cran('pak')"
RUN R -e "pak::local_install('/home/metar', ask = FALSE)"


