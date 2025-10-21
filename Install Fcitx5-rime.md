# Linux install fcitx5-rime

sudo apt install fcitx5-rime
sudo reboot

打开fcitx5配置，将中州韵添加到左面

Ctrl+～ 选择简体字
全局选项改切换输入法快捷键（默认Ctrl+空格）

皮肤目录：
~/.local/share/fcitx5/themes〔方案選單〕
没有就创建，将皮肤复制到该目录
重新启动

打开fcitx5配置->附加组件->经典用户界面->更改主题（可以看到我们的主题）
也可以更改字体大小

一路确定，就可以了

安装雾凇拼音
```
git clone --depth 1 https://github.com/rime/plum ~/plum && cd ~/plum

rime_frontend=fcitx5-rime bash rime-install iDvel/rime-ice:others/recipes/full

rm -rf ~/plum
```
重新启动
Ctrl+～ 选择雾凇拼音

