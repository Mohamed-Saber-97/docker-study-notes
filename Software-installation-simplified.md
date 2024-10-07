# Software installation simplified

## Identifying software

* Docker creates containers from images. An image is a file. It holds files that will be available to containers created
  from it and metadata about the image. This metadata contains labels, environment variables, default execution context,
  the command history for an image, and more.
* `docker.io/dockerinaction/ch3_hello_registry` is called **_Repository name_**
    * `docker.io` Registry host
    * `dockerinaction` User or organization name
    * `ch3_hello_registry` Short name
* Same image can have multiple tags

## Finding and installing software

* **_Indexes_** are search engines that catalog repositories. There are several public Docker **_indexes_**, but by
  default docker is integrated with an **_index_** named Docker Hub.
* Docker Hub is a **_registry_** and **_index_** with a web user interface run by Docker Inc. It’s the default *
  *_registry_** and **_index_** used by docker and is located at the host [docker.io](https://www.docker.com/).
* When you issue a `docker pull` or `docker run` command without specifying an alternative registry, Docker will default
  to looking for the repository on Docker Hub.
* The next few steps illustrates how to create an image from another one:
    * `docker pull busybox:latest`
        * `pull` Install an image to export
        * `busybox:latest` The image is busybox:latest small and a good example
    * `docker save -o myfile.tar busybox:latest`
        * `save` The **_save_** command exports an image
        * `-o myfile.tar` using **_-o_** you can specify the name of the output file. `.tar` can be replaced by any
          extension
        * `busybox:latest` Name of the image you want to export
    * `docker rmi busybox` to remove the image from Docker

## Installation files and isolation

* an image is actually a collection of image layers **_(intermediate images)_**.
* A layer is set of files and file metadata that is packaged and distributed as an atomic unit
* `docker images` or `docker images -a` 
* `docker rmi <image_name>`
* The first and perhaps most important benefit of this approach is that common layers need to be installed only once. 
