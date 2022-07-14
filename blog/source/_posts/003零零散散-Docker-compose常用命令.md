---
title: Docker-compose常用命令
categories: 零零散散
tags:
 - Docker-compose
---

### 1. 命令格式

```bash
docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
Parameter:
  -f，–file FILE指定Compose模板文件，默认为docker-compose.yml，可以多次指定。 
  -p，–project-name NAME指定项目名称，默认将使用所在目录名称作为项目名。 
  -x-network-driver 使用Docker的可拔插网络后端特性（需要Docker 1.9+版本） 
  -x-network-driver DRIVER指定网络后端的驱动，默认为bridge（需要Docker 1.9+版本） 
  -verbose输出更多调试信息 
  -v，–version打印版本并退出
```

### 2. 运行容器

docker-compose up [options]

```bash
Parameter:
  -d          在后台运行
  --no-color     不使用颜色区分不同的服务的控制输出
  --no-deps     不启用服务所链接的容器
  --force-recreate  强制重新创建容器，不能与–no-recreate同时使用
  -no-recreate    如果容器已经存在，则不重新创建，不能与–force-recreate同时使用
  -no-build 不自动构建缺失的服务镜像
  -build 在启动容器前构建服务镜像
  -abort-on-container-exit 停止所有容器，如果任何一个容器被停止，不能与-d同时使用
  -t, –timeout TIMEOUT 停止容器时候的超时（默认为10秒）
  -remove-orphans 删除服务中没有在compose文件中定义的容器
  -scale SERVICE=NUM 设置服务运行容器的个数，将覆盖在compose中通过scale指定的参数
  Usage:
  docker-compose up -d
  docker-compose up -d --force-recreate
```

### 3. 列出容器

3.1 列出所有运行中的容器

```bash
docker-compose ps
```

3.2 列出所有容器的id以及状态

```bash
docker ps
```

3.3 列出所有运行中容器的id

```
docker ps -aq
```

### 4. 停止容器

4.1 停止某一容器

```bash
docker-compose stop <SERVICE>
```

4.2 停止所有正在运行的容器

```bash
docker ps -aq|xargs docker stop	# docker ps -aq 列出所有ID，xargs 转交给 docker stop 停止所有容器
```

