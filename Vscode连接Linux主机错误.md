# vscode连接Linux主机错误

## 问题

vscode连接Linux主机错误:

`Failed to set up dynamic port forwarding connection over SSH to the`

**解决方法：**

在`/etc/ssh/sshd_config`添加`AllowTcpForwarding yes`或者取消原来99行左右的注释，然后重启即可

步骤如下

```
cd /etc/ssh
```

```
sudo vim sshd_config
```

```
sudo reboot
```

## 问题

安装ssh

`sudo apt install openssh-server`
