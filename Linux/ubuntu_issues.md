# 使用Ubuntu过程中遇到的问题

### Windows和Ubuntu时间同步问题

如果安装了Windows和Ubuntu双系统的话，可能会出现两个系统间时间不同步的问题。这是因为Windows采用的是**Local Time**，而Ubuntu则使用**UTC**。

#### 解决办法（以下办法选其一）

1. 在Ubuntu中解决

  - Ubuntu 16.04+

    ```bash
      timedatectl set-local-rtc 1
    ```
  - Ubuntu 15.10及更早版本，将`/etc/default/rcS`文件中的`UTC=yes`更改为`UTC=no`

    ```bash
      sudo sed -i 's/UTC=yes/UTC=no/' /etc/default/rcS
    ```
  - 以上是在Ubuntu系统中操作，还可以在Windows中更改相关设置


2. 在Windows中解决

  - 下载[windowstimefixutc.reg](http://www.linuxandubuntu.com/uploads/2/1/1/5/21152474/windowstimefixutc.reg)，然后双击
  
  - 管理员身份运行命令行工具
    ```bash
      sc config w32time start= disabled
    ```
