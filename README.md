# cdhit-docker
Docker image for running cdhit in Ubuntu 18.04

The image contains a full install of [cd-hit](http://weizhongli-lab.org/cd-hit/), including all necessary dependencies. I am not part of the developer team - I just made this image.

In detail, the image is set up with:
 - Ubuntu 18.04
 - cd-hit v4.8.1-2019-0228

To run any program from the cd-hit suite you can do the following (this will mount the directory `/in` of the container to the current working directory on your local machine, and allow you to access files in this directory and any sub-directories):
```bash
$ docker run --rm -v $(pwd):/home/in -w /in chrishah/cdhit:v4.8.1 cd-hit

$ docker run --rm -v $(pwd):/home/in -w /in chrishah/cdhit:v4.8.1 cd-hit-est
```

You can also enter the container environment and work within it. All executables should be in the `PATH`.
```bash
$ docker run -it --rm -v $(pwd):/in -w /in chrishah/cdhit:v4.8.1 /bin/bash
```
