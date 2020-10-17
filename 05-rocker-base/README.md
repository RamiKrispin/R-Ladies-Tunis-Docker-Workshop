In this case, we will repeat the build of the `tidyverse` docker, this time using base R image from rocker:

``` shell
docker build . -t rkrispin/tidyverse:rocker
```


Let's launch the docker container and test the the package version:

``` shell
docker run -t -d rkrispin/tidyverse:rocker

docker exec -it container_id /bin/sh; 
```