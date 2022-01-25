# zsh5.8 和 oh my zsh 的安装与配置
## zsh5.8 的安装与配置
### 安装 zsh5.8
```shell
cd ~
wget https://www.zsh.org/pub/zsh-5.8.tar.xz
xz -d zsh-5.8.tar.xz
tar xvf zsh-5.8.tar
./configure && make
sudo make install
```
### 查看系统支持的 shell 类型
```shell
➜  ~ cat /etc/shells 
/bin/sh
/bin/bash
/usr/bin/sh
/usr/bin/bash
/bin/tcsh
/bin/csh
/bin/ksh
/bin/rksh
/bin/zsh
```
### 查看当前使用的 shell 类型
```shell
➜  ~ echo $SHELL                                                                              
/bin/zsh
```
### 修改默认 shell 类型
```shell
➜  ~ chsh -s /bin/zsh 
Changing shell for root.
Shell changed.
```
> 修改了系统默认 shell 类型之后，不会立即生效，需要重启启动 shell。

## oh my zsh 的安装与配置
### github 仓库地址
https://github.com/ohmyzsh/ohmyzsh
### 安装 oh my zsh
```shell
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### 常用的插件
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)
- [zsh-completions](https://github.com/zsh-users/zsh-completions#oh-my-zsh)