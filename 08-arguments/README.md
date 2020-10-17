### Building docker with arguments

The docker `ARG` argument enables the user to add arguments to the build. In this example we added the following three arguments:

```
ARG major
ARG minor
ARG patch
```

We will use those argument to set the R version of the build by defining the enviroment variables with the `ENV` argument:

```
ENV R_VERSION_MAJOR ${major:-4}
ENV R_VERSION_MINOR ${minor:-0}
ENV R_VERSION_PATCH ${patch:-0}

```
where version 4.0.0 is set to default, and will be use if no argument used by the user.

For example, if we wish to build the image using R 3.6.2:

``` shell
docker build --build-arg major=3 --build-arg minor=6 --build-arg patch=2 . -t rkrispin/baser:v3.6.2
```


