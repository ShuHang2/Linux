# dpkg

## 安装本地包

```
sudo dpkg -i teamviewer_amd64.deb 
```

## 删除一个包

要删除一个包使用-r选项，或者如果您想删除它的所有文件(包括配置文件)，您可以使用—purge选项来清除它

```
sudo dpkg -r teamviewer 
sudo dpkg --purge teamviewer 
```

