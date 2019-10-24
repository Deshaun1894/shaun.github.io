---
layout: post 
title: "manjaro操作系统知识库"
thumb: /img/in-post/wiki/thumb.jpg
category: wiki
tags:  "manjaro linux wiki"
---

# 前言
最近卸载了ubuntu，安装了manjaro，简直不要太好用，安装软件真的不要太简单，现在就把一些常用的记录下来，没有从开始记录，有点遗憾，后面再补吧

# mysql
安装过程
```
sudo pacman -S mysql
# 初始化MySQL，记住输出的root密码
sudo mysqld --initialize --user=mysql --basedir=/usr --datadir=/var/lib/mysql
# 设置开机启动MySQL服务
systemctl enable mysqld.service
systemctl daemon-reload
systemctl start mysqld.service
# 使用MySQL前必须修改root密码，MySQL 8.0.15不能使用set password修改密码
mysql -u root -p
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码';
# 完成
```

# electron-ssr
- 安装 在add/remove application中搜索electron-ssr即可，然后安装
- 设置开机自启动
```
sudo ln -s /usr/share/applications/electron-ssr.desktop /etc/xdg/autostart/
```
- 配置    
[ssr免费地址](https://github.com/Alvin9999/new-pac/wiki/ss%E5%85%8D%E8%B4%B9%E8%B4%A6%E5%8F%B7)    
[gfwlist地址](https://github.com/gfwlist/gfwlist)    
[switchOmega谷歌插件地址](https://github.com/FelisCatus/SwitchyOmega/releases)    
proxy选择socks5协议，server填写127.0.0.1，端口填写1080，应用     
auto switch中删除所有的switch rules，在rule list config中填写gfwlist中的过滤地址，download profile now按钮，下载过滤地址，格式选择AutoProxy，在Switch rules中将规则列表中使用proxy模式，其他使用直接模式，保存应用即可。     
electron-ssr中直接根据ssr免费地址中的信息填写即可。
