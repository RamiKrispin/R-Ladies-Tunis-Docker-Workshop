FROM rocker/r-base:4.0.3

LABEL maintainer="Rami Krispin <rami.krispin@gmail.com>"

RUN Rscript -e "install.packages('tidyverse', repos = 'http://cran.rstudio.com/')"

ENTRYPOINT ["sh", "-c"]

CMD ["R --no-save"]