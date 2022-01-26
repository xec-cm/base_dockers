FROM rocker/tidyverse:4.1.2

# Change permissions for R library
RUN chmod -R a+rwx /usr/local/lib/R/site-library

# Install Linux dependencies for geospatial R packages
RUN apt-get update && apt-get install -y zlib1g-dev \
    libxml2-dev \
    libxt-dev \
    libcairo2-dev \
    libglpk-dev \
    libgmp3-dev \
    libmpfr-dev \
    libcurl4-gnutls-dev \
    libmysqlclient-dev \
    libjpeg-dev

ADD ./metar_deps /home/metar_deps

RUN R -e "devtools::install_cran('pak')"
RUN R -e "pak::local_install('/home/metar_deps', ask = FALSE)"


