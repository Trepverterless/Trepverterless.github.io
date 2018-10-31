---
layout: post
title: 论守塔与补兵
date: 2018-5-21 0:0:0 +0800
categories: technology
tags: kali openvas
img: https://github.com/Trepverterless/Trepverterless.github.io/raw/master/assets/images/posts/post180521.png
---
kali安装openvas中的一些问题及解决方法

* 
{:toc}
#对于kali安装openvas中的一些问题及解决方法


##安装openvas
`apt-get install openvas`</br>
apt-get，是一条linux命令，适用于deb包管理式的操作系统，主要用于自动从互联网的软件仓库中搜索、安装、升级、卸载软件或操作系统。
可能会遇到没有找到源的情况
此时要更新源
可以用`leafpad /etc/apt/sources.list`命令打开sources.list添加源，或者手动找到`/etc/apt`路径打开sources.list
然后添加<div style="background:#F0F0F0">
 #kali官方源

deb http://http.kali.org/kali kali-rolling main non-free contrib

 #中科大kali源

deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb http://mirrors.ustc.edu.cn/kali-security kali-current/updates main contrib non-free
deb-src http://mirrors.ustc.edu.cn/kali-security kali-current/updates main contrib non-free

 #阿里云kali源

deb http://mirrors.aliyun.com/kali kali-rolling main non-free contrib
deb-src http://mirrors.aliyun.com/kali kali-rolling main non-free contrib
deb http://mirrors.aliyun.com/kali-security kali-rolling/updates main contrib non-free
deb-src http://mirrors.aliyun.com/kali-security kali-rolling/updates main contrib non-free


 #163 DEBIAN源

deb http://mirrors.163.com/debian wheezy main non-free contrib 
deb-src http://mirrors.163.com/debian wheezy main non-free contrib 
deb http://mirrors.163.com/debian wheezy-proposed-updates main non-free contrib 
deb-src http://mirrors.163.com/debian wheezy-proposed-updates main non-free contrib 
deb-src http://mirrors.163.com/debian-security wheezy/updates main non-free contrib 
deb http://mirrors.163.com/debian-security wheezy/updates main non-free contrib

 #163 DEBIAN源

deb http://mirrors.163.com/debian wheezy main non-free contrib 
deb-src http://mirrors.163.com/debian wheezy main non-free contrib 
deb http://mirrors.163.com/debian wheezy-proposed-updates main non-free contrib 
deb-src http://mirrors.163.com/debian wheezy-proposed-updates main non-free contrib 
deb-src http://mirrors.163.com/debian-security wheezy/updates main non-free contrib 
deb http://mirrors.163.com/debian-security wheezy/updates main non-free contrib</div>