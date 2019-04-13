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
