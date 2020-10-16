### Creating a Base R docker

To build the image use:

``` shell
docker build . -t baser:400
```

To launch the container use:

``` shell
docker run -t -d baser:400
```

To access the container while running use:

``` shell
docker exec -it container_id /bin/sh; exit
```

To get the `container_id` use `docker container ps`
