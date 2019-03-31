# win10家庭版MySQL8.0.15+Navicat Premium12.1.11安装教程

> * 安装MySQL
> * 安装破解版Navicat Premium
> * Navicat Premium连接MySQL

## 1.安装MySQL
> MySQL官网提供两种安装方式：installer和zip，本文仅展示zip安装。[下载地址][1] 

### 1.1下载安装包
![](https://github.com/DREAMinLin/Picture/blob/master/1.jpg?raw=true)

### 1.2解压：生成的文件中不包含data和my-default.ini

### 1.3在环境变量-系统变量-path项中填加安装包的bin文件地址，例如：D:\mysql-8.0.15-winx64\bin

### 1.4在安装包bin文件下运行管理员身份命令cmd

### 1.5安装：输入mysqld --install
![min](https://img-blog.csdnimg.cn/20190228154636347.png)

### 1.6在安装根目录下新建一个my-default.ini文件，如果名称为my.ini，mysql可能会启动失败
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

### 1.7初始化：输入mysqld --initialize
> 此时安装目录下出现data文件夹，其中的后缀名为.err的文件中包含了之后会使用到的随机密码。

![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/2.jpg?token=AuQooW035ImZVKkhxvdH9aRI1H4NHOOhks5coGcSwA%3D%3D)

### 1.8启动：输入net start mysql，出现下面图样，启动成功
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/4.jpg?token=AuQooQxuzIp4M65H9fcoVcMTpr4Qqn2Aks5coGfwwA%3D%3D)

### 1.9登录：输入mysql -u root -p ，输入.err文件中的随机密码

### 1.10更改密码：输入ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码';
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/5.jpg?token=AuQooTWDvQM5VBAGWkQMuk_KdxFXwocDks5coGdYwA%3D%3D)

### 1.11验证：输入show databases; 出现如下图样
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/6.jpg?token=AuQooWmXv9wMvsLvpMEOxfu7FTTEWblEks5coGduwA%3D%3D)

### 1.12输入quit退出，再输入net stop mysql关闭服务器



## 2.安装Navicat Premium

### 2.1下载破解版安装包
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/1.jpg?token=AuQooaWfFC1Km9ywwyYdXK3zZxLfZCtOks5coG0KwA%3D%3D)
> 运行.exe文件，安装Navicat
> 解压.rar文件，运行.exe文件，进行破解

**注：打开注册机前请不要打开navicat，另外请断网进行破解操作**

### 2.2首先选择patch，再打开navicat
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/2.jpg?token=AuQooepL4kyG_EMiKp5nhlcndANL3m85ks5coG0kwA%3D%3D)

### 2.3打开navicat，帮助——>注册
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/3.jpg?token=AuQooVOlRZ0h8-okV946pQ2NE7LNe_rOks5coG0vwA%3D%3D)
> 将生成的注册码填入

### 2.4点击激活、手动激活
![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/4.jpg?token=AuQoodfx_ItaJ2VaEDRlGc-MLO197NV7ks5coG06wA%3D%3D)

### 2.5注册机手动激活
> 1.请求码复制到注册机
> 2.在注册机生成激活码
> 3.将激活码复制到Navicat
> 4.完成激活

![](https://raw.githubusercontent.com/DREAMinLin/Picture/master/5.jpg?token=AuQooX9Sd5ba8yfZML9T61X6cKMjTPq1ks5coG1UwA%3D%3D)






[1]: https://dev.mysql.com/downloads/mysql/
