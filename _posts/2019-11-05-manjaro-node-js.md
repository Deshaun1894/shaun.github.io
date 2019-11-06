---
layout: post 
title: "manjaro安装NodeJS"
thumb: /img/in-post/wiki/thumb.jpg
category: wiki
tags:  "manjaro NodeJS npm"
---
# 安装NodeJS
```
pacman -Ss nodejs-lts   //查看nodejs长期支持版
sudo pacman -S nodejs-lts-dubnium   //选择其中一个版本进行安装
npm -v  //查看安装成功没有，如果没有成功执行下条命令
sudo pacman -S npm
```

# 配置npm
```
npm config list //查看npm配置
npm config set prefix "{global_dir}"    //设置全局npm安装路径
npm config set cache ""     //设置全局缓存路径
npm config set registry https://registry.npm.taobao.org     //设置淘宝镜像源
```
以上的set改成get可以查看配置的参数

如果需要在bash或者zsh执行npm安装的组件，需要添加把刚刚的全局安装路径下的bin目录添加到环境变量
```
vim ~/.zshrc  //bash就是.bashrc
export PATH="{global_dir}/bin:$PATH"    //添加到环境变量
source ~/.zshrc
```

# vue初始化
```
npm install -g vue-cli  //vue手脚架
vue init webpack my-project //使用webpack模板初始化
cd my-project
npm install //安装依赖的组件
npm run dev //运行项目，用浏览器打开http://localhost:8080
```