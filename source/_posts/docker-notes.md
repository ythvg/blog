---
title: Docker学习笔记
date: 2018-06-25 19:03:58
tags:
---

- - -

### Docker镜像

* 获取镜像

    ```
    docker pull NAME[:TAG]
    e.g. docker pull ubuntu:latest
    ```

* 查看镜像信息

    ```
    docker images

    # 详细
    docker inspect ID
    ```

* 添加镜像标签

    ```
    docker tag TGNAME NAME
    ```

* 搜寻镜像

    ```
    docker search NAME
    ```

* 删除镜像

    ```
    docker rmi NAME|ID
    ```

* 创建镜像

    ```
    # 基于已有的容器创建 -m --author, -a --author, 
    docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
    e.g. docker commit -m "Added a new file" -a "jim.fun" 0f99624 test

    ```

* 上传镜像

    ```
    docker push NAME:[TAG]
    ```


### Docker容器

* 启动容器

    ```
    docker run NAME
    e.g. docker run -ti ubuntu /bin/bash 
    ```

### Docker仓库