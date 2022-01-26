FROM rocker/tidyverse::4.1.2

ADD ./metar_deps /home/metar

RUN R -e "devtools::install_cran('pak')"
RUN R -e "pak::local_install('/home/metar', ask = FALSE)"


