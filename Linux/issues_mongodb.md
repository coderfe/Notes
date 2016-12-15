# Fedora 安装 MongoDB

最近从 Ubuntu 转到 Fedora ，虽然都属于 Linux ，但是感觉还是有点不适应，尤其是 **apt => dnf** 的变化。昨晚在安装 MongoDB 的时候出现了一系列的问题，但是在经历了这一系列的折腾之后，终于成功安装了 MongoDB ，恰好也熟悉了 dnf 命令行。

## 添加源

在官网上没有针对 Fedora 的安装教程，但是我们可以参考 Red Hat 的安装教程。

- 创建文件，安装 3.3 版本

  ```shell
  sudo vim /etc/yum.repos.d/mongodb-org.repo
  # 内容如下
  [mongodb-org]
  name=MongoDB Repository
  baseurl=https://repo.mongodb.org/yum/redhat/5Server/mongodb-org/3.3/x86_64
  gpgcheck=1
  enabled=1
  gpgkey=https://www.mongodb.org/static/pgp/server-3.3.asc
  ```

- dnf 命令安装 MongoDB

  ```shell
  sudo dnf install mongodb-org
  ```

## 报错处理

如果不出意外，当启动 mongod 服务时会出现一个报错信息。这时就需要设置一下 **SELinux** 了。

- 更改 /etc/selinux/config 配置

  ```shell
  sudo vim /etc/selinux/config
  # 1.更改 SELINUX=enforcing => SELINUX=disabled
  # 1.更改 SELINUX=enforcing => SELINUX=permissive
  ```

## 使用 MongoDB

- mongod 服务的启动 / 重启 / 关闭 / 状态

  ```shell
  # 启动
  sudo service mongod start
  # 重启
  sudo service mongod restart
  # 关闭
  sudo service mongod stop
  # 状态
  sudo service mongod status
  ```

- mongo-shell 的使用

  ```shell

  ```

  ​