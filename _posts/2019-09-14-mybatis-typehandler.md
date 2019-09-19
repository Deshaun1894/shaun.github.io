---
layout: post 
title: "mybatis数据结果类型处理"
thumb: /img/in-post/java/thumb.png
category: tech
tags:  "java mybatis typehandler"
---
# 前言
在使用mybatis对数据库进行操作的时候，常常会遇到一些分类变量以及数据库中的某些char字段取出来需要trim的情况，对于这些情况，如果我们在使用取出数据后再一一处理，则会显得较为麻烦，幸好mybatis有一个typehandler类，可以对数据在取出的时候就进行转换处理，这样避免了后续的代码繁琐。
# 代码实现
