### Installing additional packages

In this example we will install the **tidyverse** packages on top of the `baser:400` image. This time we will set the `reops` argument:

``` shell
docker build . -t rkrispin/tidyverse:latest
```

As we saw before, to launch the container use:

``` shell
docker run -t -d rkrispin/tidyverse:latest
```

And to access the container while running use:

``` shell
docker exec -it container_id /bin/sh;
```

Where the `container_id` can be found by running `docker container ps`