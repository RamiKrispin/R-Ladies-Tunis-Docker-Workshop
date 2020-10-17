### Setting RStudio enviroment in Docker

Setting RStudio within a Docker environment enables you to create a development and/or testing environment for your dockers images. In this example, we will build an RStudio working environment on top of the `tidyverse` image we created before:

``` shell
docker build . -t rkrispin/rstudio:tidyverse
```

To launch the docker on a browser we will use the `-p` argument to set the ports of the localhost:

``` shell
docker run --rm -p 8787:8787 -e PASSWORD=1234 -e USER=rami rkrispin/rstudio:tidyverse
```

As we defined on the `Dockerfile` to expose the container to port `8787` we will map it to the local port `8787` (although you can map it to any other available port on your machine). The RStudio instance required username and password, so we will use the `PASSWORD` and `USER` argument to define them. Once launch the container, you can access RStudio on your browser using `http://localhost:8787/`