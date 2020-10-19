### This example will fail...

After creating a base R image, in this example we will try to build on top of `baser:400` a new image with the `tidyverse` packages:

``` shell
docker build . -t rkrispin/tidyverse:latest
```

This build will fail, as we did not configurate the `ropos` option, and therefore, the `install.packages` command fail. In the following next we will solve it 
