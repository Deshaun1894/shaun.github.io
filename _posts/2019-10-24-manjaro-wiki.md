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