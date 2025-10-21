# openssh连接树莓派

系统：windows10

## windows端打开openssh服务

设置->系统--左侧边栏-->可选功能->添加功能

添加OpenSSH 客户端、OpenSSH服务器

![image-20250220120719886](./img/image-20250220120719886.png)

## 连接到树莓派（密匙）

```
ssh UserName@IpAddress -p 22
```

e.g：`ssh shuhang2@192.168.31.8 -p 22`
