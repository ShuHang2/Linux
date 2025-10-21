# Change to sudoer
su -
visudo
```
zzz ALL=(ALL:ALL)
```

# ADD tsinghua address

sudo nano /etc/apt/sources.list 

```
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ testing main contrib non-free non-free-firmware
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ testing main contrib non-free non-free-firmware

deb https://mirrors.tuna.tsinghua.edu.cn/debian/ testing-updates main contrib non-free non-free-firmware
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ testing-updates main contrib non-free non-free-firmware

deb https://mirrors.tuna.tsinghua.edu.cn/debian/ testing-backports main contrib non-free non-free-firmware
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ testing-backports main contrib non-free non-free-firmware

deb https://security.debian.org/debian-security testing-security main contrib non-free non-free-firmware
# deb-src https://security.debian.org/debian-security testing-security main contrib non-free non-free-firmware
```

# Update

apt update && apt upgrade

# install nvidia
https://wiki.debian.org/NvidiaGraphicsDrivers
sudo apt install linux-headers-amd64
install_items+=" /etc/modprobe.d/nvidia-blacklists-nouveau.conf /etc/modprobe.d/nvidia.conf /etc/modprobe.d/nvidia-options.conf "

sudo apt install nvidia-kernel-dkms nvidia-driver firmware-misc-nonfree

## Wayland
echo "options nvidia-drm modeset=1" >> /etc/modprobe.d/nvidia-options.conf
echo "options nvidia NVreg_PreserveVideoMemoryAllocations=1" >> /etc/modprobe.d/nvidia-options.conf

sudo reboot
# shut up bee~~~

sudo nano /etc/inputrc

```
set bell-style none
```

sudo nano /etc/modprobe.d/blacklist.conf
```
blacklist pcspkr
```

# Startup light
Question:rc-local service don's start
Answer:https://u.sb/debian-rc-local/

set light 75 when start computer

sudo nano /etc/rc.local

```
#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

echo "75" | sudo tee /sys/class/backlight/*/brightness >/dev/null

exit 0
EOF
```
chmod +x /etc/rc.local
systemctl enable --now rc-local

systemctl status rc-local.service # check if rc.cocal starts

# install git

```
sudo apt install git

git config --global user.name "shuhang2"
git config --global user.email "shuhang2@qq.com"
git config list
```

# install zsh and beauty
Attention:it use github source,maybe need vpn or other tools

```
sudo apt install zsh
chsh -s /bin/zsh

turn off and open window

apt install wget

sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
# imrror
sh -c "$(wget -O- https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
cd ~/.oh-my-zsh/themes && ls

git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/valentinocossar/vscode.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh/vscode

nano ~/.zshrc

ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(git zsh-syntax-highlighting zsh-autosuggestions vscode)

source ~/.zshrc

p10k configure #重新配置

```
# install timeshift
sudo apt install timeshift

sudo timeshift-launcher

# change gtk theme
https://github.com/vinceliuice/Orchis-theme

git clone https://github.com/vinceliuice/Orchis-theme.git
cd Orchis-theme/ 
./install.sh
cd ..
rm -rf Orchis-theme/

# install v2vay

git clone https://github.com/v2fly/fhs-install-v2ray.git
cd fhs-install-v2ray/
sudo bash ./install-release.sh

systemctl enable v2ray
systemctl start v2ray

sudo dpkg -i ./installer_debian_x64_2.2.6.7.deb

sudo systemctl start v2raya.service
sudo systemctl enable v2raya.service

cd ..
rm -rf fhs-install-v2ray
