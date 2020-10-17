FROM rocker/r-base:4.0.3

LABEL maintainer="Rami Krispin <rami.krispin@gmail.com>"

# https://github.com/eddelbuettel/littler/blob/master/inst/examples/install2.r

# Install data packages
RUN install2.r --error \
  lubridate \
  magrittr \
  dplyr \
  tidyr \
  purrr \
  data.table 
  
# Install modeling packages
RUN install2.r --error \
  forecast \
  tsibble \
  fable

# Install viz tools packages
RUN install2.r --error \
  ggplot2 \
  plotly
  
