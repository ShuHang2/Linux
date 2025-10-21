# ssh连接

## 密钥

公钥生成

```
ssh-keygen -t rsa -b 4096 -C "shuhang2@qq.com"
```

**-t rsa**：指定密钥类型为RSA
**-b 4096**：指定密钥长度为4096位
**-C “your_email@example.com”**：添加注释（通常是您的电子邮件地址），这有助于识别密钥

生成位置：`C:\Users\yourcomputername\.ssh`

```
id_rsa  # 私钥文件
id_rsa.pub  # 公钥文件
```

## 使用

```
cd ~
mkdir .ssh
cd .ssh
touch authorized_keys
```

将`id_rsa.pub`内容插入`authorized_keys`中
