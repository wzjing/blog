# Ubunu环境变量详解
## 系统级环境变量
* /etc/profile
用户第一次登陆时使用此文件初始环境，内部又很多/etc/bash.bashrc的调用
* /etc/bash.bashrc
运行bash shell时首先读取该文件
* /etc/environment
系统最根本的环境变量设置
## 用户级环境变量
~/.profile
系统变量加载完成后，此文件首先被加载
~/.bashrc
用打开bash shell时会执行此文件
~/.bash_profile
用户登陆后次文件只执行一次，之后用来调用~/.bashrc
~/.bash_login
只作用于非图形界面
~/.pam_environment
用户的环境变量设置