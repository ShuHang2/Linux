# WSL

## Linux子系统安装

在windows中启用**适用于Linux的Windows子系统**、**虚拟机平台**

<img src="./img/image-20241221234208026.png" alt="image-20241221234208026" style="zoom:50%;" />

使用管理员运行CMD，输入`wsl --install Debian --web-download`，下载Debian系统

Ps：也可以使用`wsl --list -online`，查看所有可以安装的Linux系统

<img src="./img/image-20241221234457197.png" alt="image-20241221234457197" style="zoom: 67%;" />

输入用户名、密码

<img src="./img/image-20241221234550013.png" alt="image-20241221234550013" style="zoom:67%;" />

## 启动停止Linux子系统

查看Linux子系统：`wsl --list -v`

<img src="./img/image-20241221235120088.png" alt="image-20241221235120088" style="zoom:67%;" />

设置默认子系统：`wsl --set-default Debian`

启动Linux子系统：`wsl -d Debian`

<img src="./img/image-20241221235249717.png" alt="image-20241221235249717" style="zoom:67%;" />

删除Linux子系统：`wsl --unregister Debian`