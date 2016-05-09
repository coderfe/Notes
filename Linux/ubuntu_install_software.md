# Ubuntu下软件的安装配置
## 安装 `Nodejs(4.2.3)`
1. 通过浏览器下载`Nodejs`压缩包,移动到想要安装的文件夹`sudo mv nodejs /path/to/folder`
2. 打开终端`tar -zxf name.tar.gz`解压
3. 配置环境变量
    * 打开文件`sudo gedit /etc/profile`
    * 加入参数
   ```
      export NODE_HOME=/path/to/nodejs
      export NODE_PATH=$NODE_HOME/lib/node_moudles
      export PATH=$PATH:$NODE_HOME/bin
   ```

## 安装 `Git`
```
  sudo add-apt-repository ppa:git-core/ppa
  sudo apt-get update
  sudo apt-get install git
```

## 安装 `fish`
```
  sudo apt-get install fish
```
将 `fish` 设置为默认 **Bash**
```
  chsh -s /usr/bin/fish
```
