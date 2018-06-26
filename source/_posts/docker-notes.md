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
    e.g. docker run -t -i ubuntu /bin/bash
    -t 分配一个伪终端并绑定到标准输入，-i 让容器的标准输入保持打开, -d Daemonized 守护态运行
    ```

* 终止容器

    ```
    docker stop ID
    ```

* 重启容器

    ```
    docker restart ID
    ```

* 进入容器

    ```
    docker exec [OPTIONS] ID

* 删除容器

    ```
    docker rm [OPTIONS] CONTAINER

* 导出和导入容器

    windows env get some problems


### Docker仓库

* [Docker HUb](https://hub.docker.com/)


