# MySQL

用 Docker 在本地创建一个 MySQL 容器

### 1. 下载镜像

从 [Docker Hub](https://hub.docker.com/) 找合适的镜像，一般用官方最新镜像就行

```bash
docker image pull mysql
```

光用命令行操作镜像和容器可能不太方便，可以用 Docker 自带的 GUI 或者 VSCode、IDEA 自带或者插件提供的管理功能


### 2. 创建容器

凡是创建容器，都得考虑网络端口映射、数据存储、目录挂载、环境变量这些基本配置，常用的配置在 [Docker Hub](https://hub.docker.com/) 镜像主页有说明可以参考

#### 2.1 网络

MySQL 服务默认使用 3306 端口

```bash
docker container run \
    --name mysql-local \
    -p 3306:3306 \
    -d mysql
```

#### 2.2 环境变量

创建 MySQL 容器的时候，最好设置 root 用户密码

```bash
docker container run \
    --name mysql-local \
    -p 3306:3306 \
    -e MYSQL_ROOT_PASSWORD=root \
    -d mysql
```

| 变量名 | 意义 |
| :-- | :-- |
| `MYSQL_ROOT_PASSWORD` | 必须。用于设置 MySQL root 用户的密码。 |
| `MYSQL_DATABASE` | 可选。用于指定镜像启动容器时要创建的数据库。如果提供了用户/密码，则会将该用户做为此数据库的超级用户。 |
| `MYSQL_USER`，`MYSQL_PASSWORD` | 可选。用于创建一个新用户并设置密码。 |
| `MYSQL_ALLOW_EMPTY_PASSWORD` | 可选。设置为 `yes` 时，则可以使用空密码登录。|
| `MYSQL_RANDOM_ROOT_PASSWORD` | 可选。设置为 `yes` 时会为 root 用户设置一个随机密码（使用pwgen），所生成的随机密码会被输出到stdout。 |
| `MYSQL_ONETIME_PASSWORD` | 可选。为 root 用户指定一个一次性密码，该密码会在用户首次登录时强制修改。 |


