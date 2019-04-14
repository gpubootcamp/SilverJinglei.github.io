# Shell command
sudo dpkg-reconfigure gdm3  : config boot script; gdm3 is gnome boost manager, lightdm - xubuntu boost manager
gksudo bum : run bum (boost ui manager)
ps  : processes list
sudo update-rc.d shadowsocks defaults 100 : load => boost

# Environment
/etc/inti.d/  : boost dir

# Uninstall 
原文：https://blog.csdn.net/tangsl388/article/details/79119757 

ubuntu使用apt-get install是一个很简单的东西，但是有时因为各种原因，apt-get安装一半的时候安装失败了，这时候需要卸载之前安装的，关于ubuntu卸载安装包的方法很多。
=> resolve any unstable installation

## 删除软件
### 如果你知道要删除软件的具体名称，可以使用               
sudo apt-get remove --purge 软件名称  
sudo apt-get autoremove --purge 软件名称 

### 如果不知道要删除软件的具体名称，可以使用
dpkg --get-selections | grep ‘软件相关名称’
sudo apt-get purge 一个带core的package，如果没有带core的package，则是情况而定。

### 在无法卸载又无法安装的情况下。强制卸载
卸载时问题： package is in a very bad inconsistent state; you should  reinstall it before attempting configuration， 而又无法重新安装
解决：sudo dpkg --remove --force-remove-reinstreq  软件名称

## 清理残留数据
dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P 


# ShadowSocket-libev
## 安装shadow$ocks-libev

sudo apt-get install software-properties-common -y
sudo add-apt-repository ppa:max-c-lv/shadowsocks-libev -y
sudo apt-get update
sudo apt install shadowsocks-libev 

## config
sudo vi /etc/shadowsocks-libev.json

在配置文件中输入以下信息：
{
"server":"XXXX服务器地址",
"server_port":XXXX端口,
"local_address":"127.0.0.1",
"local_port":1080,
"password":"XXXX密码",
"timeout":60,
"method":"chacha20-ietf-poly1305",
"fast_open":false,
"workers":1
}

## 设置全局代理

进入 系统设置 -> 网络 -> 网络代理，方法选择手动，然后设置Socks主机127.0.0.1， 后面端口这是1080，然后点击应用到整个系统，输入密码即可。
缺点： 这样你使用的网络都是通过代理访问的，比如说我在登录微信的时候，居然提示我在未知地点登录，这样比较浪费流量，访问国内网络也使用代理，会导致访问国内网络网速较慢。所以可以使用浏览器代理，只在浏览器访问中使用代理。

## 设置开机自启动

sudo vi shadowsocks #创建开机启动服务，其内容如下：
#!/bin/bash
/usr/bin/ss-local -c /etc/shadowsocks-libev.json
exit 0
保存文件；
赋予可执行权限：
sudo chmod +x shadowsocks
移动到/etc/init.d/ 目录下：
sudo mv shadowsocks /etc/init.d/
设置开机自启动:
sudo update-rc.d shadowsocks defaults 100


## Firefox
install [Proxy SwitchyOmega] plugin
set default protocal => SOCKS5
