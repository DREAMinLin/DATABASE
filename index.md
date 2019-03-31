# win10家庭版下MySQL8.0.15+Navicat Premium12.1.11安装教程

------
> * 安装MySQL
> * 安装Navicat Premium
> * 破解Navicat Premium
> * Navicat Premium连接MySQL

## 安装MySQL

> MySQL官网提供两种安装方式：installer和zip，本文仅展示zip安装。[下载地址][1] 

### 1.下载安装包
！[]（https://github.com/DREAMinLin/Picture/blob/master/1.jpg?raw=true）

不用注册、登录，直接选择左下按钮下载：No thanks,just start my download。
### 2.解压：生成的文件中不包含data和my-default.ini
### 3.在环境变量-系统变量-path项中填加安装包的bin文件地址，例如：D:\mysql-8.0.15-winx64\bin
### 4.在安装包bin文件下运行管理员身份命令cmd
### 5.安装：输入mysqld --install
![min](https://img-blog.csdnimg.cn/20190228154636347.png)
### 6.在安装根目录下新建一个my-default.ini文件，如果名称为my.ini，mysql可能会启动失败
>在桌面新建txt文档，写入以下代码
**注意：basedir和datadir路径需要更改为自己的安装包路径和一个还未生成的data文件路径（和bin同级）**
```
[mysqld]
port=3306
basedir=C:\Program Files (x86)\MySQL
datadir=C:\Program Files (x86)\MySQL\Data
max_connections=200
max_connect_errors=10
character-set-server=utf8
default-storage-engine=INNODB
default_authentication_plugin=mysql_native_password
[mysql]
default-character-set=utf8
[client]
port=3306
default-character-set=utf8
```
### 7.初始化：输入mysqld --initialize
此时安装目录下出现data文件夹，其中的后缀名为.err的文件中包含了之后会使用到的随机密码。
https://img-blog.csdnimg.cn/20190228155012264.png
### 8.启动：输入net start mysql，出现下面图样，启动成功
https://img-blog.csdnimg.cn/20190228155140973.png
### 9.登录：输入mysql -u root -p ，输入.err文件中的随机密码
### 10.更改密码：输入ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码';
https://img-blog.csdnimg.cn/20190228165008731.png
### 11.验证：输入show databases; 出现如下图样
https://img-blog.csdnimg.cn/20190228165315723.png
### 12.输入quit退出，再输入net stop mysql关闭服务器


[1]: https://dev.mysql.com/downloads/mysql/
