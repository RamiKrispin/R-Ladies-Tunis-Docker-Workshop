### Creating a Base R docker

To build the image use:

``` shell
docker build . -t rkrispin/baser:400
```
Build arguments:

* `.` - enables to use any file in the root folder
* `-t` - Name and optionally a tag in the `name:tag` format
* `docker build` arguments documentation - https://docs.docker.com/engine/reference/commandline/build/

Where `rkrispin` is the Ducker Hub address, `baser` is the image name, and `400` is the image tag. You can use also `docker build . -t baser:400`, but then you will have to retag it before pushing it to Docker Hub


To push the docker to Docker Hub use:

```
docker push rkrispin/baser:400
```

To launch the container use:

``` shell
docker run -t -d rkrispin/baser:400
```

* `-t` - Allocate a pseudo-TTY
* `-d` - Run container in background and print container ID
* `docker run` arguments documentation - https://docs.docker.com/engine/reference/commandline/run/

To access the container while running use:

``` shell
docker exec -it container_id /bin/sh;
```

To get the `container_id` use `docker container ps`
