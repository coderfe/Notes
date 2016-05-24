# Ubuntu下Nodejs的安装配置

> 在Ubuntu16+版本以上，可以使用apt来代替apt-get

## 安装 `Nodejs6.0.0+`
### 离线安装包方式
1. 通过浏览器下载`Nodejs`压缩包,移动到想要安装的文件夹
2. 解压`tar -zxf nodejspack.tar.gz`
3. 配置环境变量
    * 打开文件`sudo gedit /etc/profile`
    * 加入以下参数
   ```bash
      export NODE_HOME=/path/to/nodejs
      export NODE_PATH=$NODE_HOME/lib/node_moudles
      export PATH=$PATH:$NODE_HOME/bin
   ```

### 利用`nvm`安装
1. 安装，[nvm GitHub](https://github.com/creationix/nvm)
```bash
# 默认安装路径
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh | bash
# 自定义路径
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh | NVM_DIR="path/to/nvm" bash
```
2. 使用
```bash
# 安装最新版本node
$ nvm install 6.0
```
`nvm`貌似不支持`fish shell`
