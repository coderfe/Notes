# 免密码登陆远程服务器

通常从本地登陆远程的服务器，每次都要输入密码，比较麻烦。但是通过配置 ssh 则可以省略掉这一步。

## 配置

1. 在本地通过命令行生成 **RSA key** ，非常简单只要几个回车键就可以搞定！

   ```shell
   ssh-keygen
   ```

2. 生成之后，可以在 `/home/.ssh` 目录下查看。

   - `~/.ssh/id_rsa` 是私钥，注意保密，不能泄露。
   - `~/.ssh/id_rsa_pub` 是公钥，也就是要上传到远程服务器的。

3. 使用 `ssh-copy-id` 上传公钥。

   ```shell
   ssh-copy-id user@remote_host
   ```

4. 测试，免密码登陆远程服务器。

   ```shell
   ssh user@remote_host
   ```


## 关于 ssh-keygen

- `ssh-keygen -b` 生成安全性更好的 RSA key 。
- 更多的 `ssh` 命令可以通过命令行查看帮助。