FROM jenkins

MAINTAINER jianx<jianx70687547@gmail.com>

USER root
ARG dockerGid=999

RUN echo "docker:x:${dockerGid}:jenkins" >> /etc/group

# 安装 docker-compose   启动的时候植入docker： -v /var/run/docker.sock:/var/run/docker.sock  -v $(which docker):/bin/docker
RUN curl -L https://github.com/docker/compose/releases/download/2.2.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose
CMD ["docker-compose", "-v"]
# 安装 jdk11

# 安装 maven
RUN mkdir -p /opt/maven/apache-maven-3.6.3 && curl -L https://archive.apache.org/dist/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz -o /opt/maven/apache-maven-3.6.3-bin.tar.gz && tar -zxvf /opt/maven/apache-maven-3.6.3-bin.tar.gz -C /opt/maven/
COPY settings.xml /opt/apache-maven-3.6.3/conf/
ENV PATH /opt/apache-maven-3.6.3/bin:$PATH
CMD ["mvn", "-version"]

# 格式：docker build -t 镜像名称:tag标识 .