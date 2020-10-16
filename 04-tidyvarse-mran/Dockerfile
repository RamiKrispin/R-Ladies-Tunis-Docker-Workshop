FROM rkrispin/baser:400

LABEL maintainer="Rami Krispin <rami.krispin@gmail.com>"

RUN Rscript -e "install.packages('tidyverse', repos='https://mran.microsoft.com/snapshot/2019-11-01/')"

RUN Rscript -e "packageVersion('tidyverse')"