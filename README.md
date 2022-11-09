# my-docker

dcoker构建方式集合

## Dockerfile 模板
```
# FROM 指令 -- 指定即将制作的镜像，继承哪位镜像.
# 格式：FROM <image> 或 FROM <image>:<tag>
FROM jenkins

# MAINTAINER 指令 -- 指定维护者信息.
# 格式：MAINTAINER <name>
MAINTAINER jianx<jianx70687547@gmail.com>

# RUN 指令 -- 执行shell命令的，当解析Dockerfile时，遇到RUN指令，将自动翻译为/bin/sh -c “xxxx”.
# 格式：RUN <command>
RUN

# CMD 指令 -- 指启动容器时执行的命令，每个Dockerfile只能有一条CMD指令，如果指定了多条CMD，只有最后一条会被执行.
#(特别说明，如果用户启动容器时制订了运行的命令，则会覆盖掉CMD指定的指令)
# 格式：1. CMD command param1 param2   2. CMD [“executable”,”param1”,”param2”]   3. CMD [“param1”,”param2”]
CMD

# ENV 指令 -- 指定一个环境变量,会被后续的RUN指令使用，并在容器运行时保持.
# 格式：ENV <key> <value>
ENV

# ADD 指令 -- 复制指定<src>到容器中的<dest>中，可以是Dockerfile所在目录的一个相对路径，也可以是一个URL，还可以是一个tar文件（自动解压为目录）.
# 格式：ADD <src> <dest>
ADD

# COPY 指令 -- 复制本地主机<src>到容器中的<dest>中，当使用本地目录为源目录时，推荐使用.
# 格式：COPY <src> <dest>
COPY

# ENTRYPOINT 指令 -- 指启动容器时执行的命令，每个Dockerfile只能有一条CMD指令，如果指定了多条CMD，每一条命令追加被执行.
# 格式：1. ENTRYPOINT command param1 param2   2. ENTRYPOINT [“executable”,”param1”,”param2”]   3. ENTRYPOINT [“param1”,”param2”]
ENTRYPOINT


# 最后退出Dockerfile进行构建镜像.
# 格式：docker build -t 镜像名称:tag标识 .
```

## 阿里云Docker Registry
```shell
# 目前最新有 frps-0.40.0
docker pull registry.cn-hangzhou.aliyuncs.com/jianx/frp:[镜像版本号]
```

## 当前的访问地址有以下几种方式：
- [gitea](http://gitea.frp.jianx.top/jianx/my-docker)

<img data-modal-trigger="badge-modal" src="https://img.shields.io/badge/Stars-5-blue?logo=gitea&style=social">

- [gitee](https://gitee.com/jtop-cloud/my-docker)

<img data-modal-trigger="badge-modal" src="https://img.shields.io/badge/Stars-143-blue?logo=gitee&style=social">

- [github](https://github.com/70687547/my-docker)

<img data-modal-trigger="badge-modal" src="https://img.shields.io/badge/Stars-26-blue?logo=github&style=social">