---
layout: post
title: Dockerize Scrapy based on MongoDB
description: Make an dockerfile that create an image with Scrapy, MongoDB based on Python2
category: ProgrammingThinking
tags: summary
---

这篇文章的目的是创建一个dokcer镜像用来做为使用爬虫框架Scrapy的环境。

## Why

使用Python的爬虫框架Scrapy爬取，用非关系型数据库MongoDB存储数据，这个对于一个简单的爬虫系统
来说再好不过了，但是遇到一个问题，之前我在本地的机器上话了一小段时间来安装环境，当我想把代码
在远程机器上使用时，我又要再装一次环境，blabla，还是弄一个docker镜像吧，方便又实用。

## How

鉴于docker官法已经有一个MongoDB的image，我们从这个image开始构建我们的image。

```
# Dockerfile for Scrapy + MongoDB + Python

# use the official mongodb image
FROM mongo
MAINTAINER Chris Qiu <qwh005007@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

# Install Python and libs
RUN apt-get update && \
    apt-get install -y python python-dev python-pip python-virtualenv python-setuptools && \
    apt-get install -y build-essential libxml2-dev libxslt1-dev libffi-dev libssl-dev
RUN pip install requests scrapy service_identity pymongo scrapy-mongodb lxml w3lib cssselect twisted beautifulsoup4 queuelib
RUN rm -rf /var/lib/apt/lists/* && \
    rm -rf /usr/local/lib/python2.7/dist-packages/requests && \
    rm -rf /tmp/*

WORKDIR /data
CMD ["bash"]

# Expose ports.
#  mongo - 27017: process
#  mongo - 28017: http
#  scrapy Telnet 6023
#  scrapy Web service 6080
EXPOSE 27017 28017 6023 6080
```

上面的Dockerfile使用了mongo作为基础镜像，再这个镜像基础上Scrapy以及Python控制mongodb的
模块pymongo等相关的模块和lib。

## Where

写完Dockerfile大可以直接在本地build，但是这会花费很长时间，是的，如果网络差一点，这个就真的很令人
伤脑筋，所以我使用docker提供的AutomatedBuild方式来build这个镜像。

首先将写好的Dockerfile push到github上，然后在Docker Hub中使用`Add Repository -> Automated Build`，
连接上你的github账号，然后选择刚push的Dockerfile项目，然后create images，这样，一段时间之后就可以。

可以从repository页面中看到building的进度，一但完成就可以使用`docker pull <repository-name>`获取这个镜像了。

详细文档可以从这个官方文档中得到：[Automated Builds on Docker Hub](https://docs.docker.com/docker-hub/builds/)

## Further

更进一步，如果要在上面的环境中加入Redis来构成一个分布式的爬虫系统也是非常有意思的。

The END.
