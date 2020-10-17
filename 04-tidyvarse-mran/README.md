### Looking down the package version

**Problem:** as you keep refreshing the docker image, it will install the latest package version available on CRAN. That not necessarily the version you tested when built the first version. The main issue that in newer versions, some functions will be changed or deprecated. 

**Solution:** To avoid this, you can set the package version by using Microsoft [MRAN](https://mran.microsoft.com/) snapshot based on a specific date. In the previous example, we installed the latest version of the tidyverse package (as of Oct 2020), version 1.3.0, which was released on November 21st, 2019. Let's assume we want to install and look down version 1.2.1, then, using MRAN snapshot from any date before the release date of version 1.3.0 (and after the release date of the previous version, 1.2.1) will ensure that on any rebuilt of the docker image the same package version install. This time we will use different tagging:

``` shell
docker build . -t rkrispin/tidyverse:mran
```


Let's lanch the docker container and test the the package version:

``` shell
docker run -t -d rkrispin/tidyverse:latest

docker exec -it container_id /bin/sh; 
```

