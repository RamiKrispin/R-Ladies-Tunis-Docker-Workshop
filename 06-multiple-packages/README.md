### Install multiple R packages

Using the `RUN Rscript -e "install.packages(...)` function might be too convoluted when we wish to install dozens of packages. A more simple way could be with the `install2.r` function. In this example, we will simplify the installation of the packages by categories (e.g., data and utility, modeling, visualization). 

```
docker build . -t rkrispin/baser:multiple_packages
```

Let's try to add additional package and rerun the build.