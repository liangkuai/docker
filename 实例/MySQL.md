# MySQL

### 环境变量

当启动 MySQL 容器时，我们可以向 docker run 命令传入一或多个环境变量来调整 MySQL 实例的配置。


|变量名|意义|
|:--|:--|
|MYSQL_ROOT_PASSWORD|必须。用于设置 MySQL root 用户的密码。|
|MYSQL_DATABASE|可选。用于指定镜像启动容器时要创建的数据库。如果提供了用户/密码，则会将该用户做为此数据库的超级用户。|
|MYSQL_USER，MYSQL_PASSWORD|可选。用于创建一个新用户并设置密码。|
|MYSQL_ALLOW_EMPTY_PASSWORD|可选。设置为yes时，则可以使用空密码登录。|
|MYSQL_RANDOM_ROOT_PASSWORD|可选。设置为yes时会为 root 用户设置一个随机密码（使用pwgen），所生成的随机密码会被输出到stdout。|
|MYSQL_ONETIME_PASSWORD|可选。为root用户指定一个一次性密码，该密码会在用户首次登录时强制修改。|

