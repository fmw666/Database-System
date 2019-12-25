# MySQL 指南
>> 学习视频地址：[百度云](https://pan.baidu.com/s/1Xn78u1Npxe_YNJEfgJn3xA#list/path=%2F)，密码：`79sm`，⚡特此说明！
<hr/>

*`MySQL`是一个[关系型数据库管理系统]()，由瑞典 MySQL AB 公司开发，目前属于 [Oracle]() 旗下产品。`MySQL` 是最流行的[关系型数据库管理系统]()之一，在 WEB 应用方面，`MySQL`是最好的 [RDBMS]() (Relational Database Management System，关系数据库管理系统) 应用软件。*

> **MySQL下载与安装**: 来自[weixin_40396510](https://blog.csdn.net/weixin_40396510/article/details/79277731)的CSDN博客。 

[![Downloads](https://img.shields.io/npm/dm/eslint-config-airbnb.svg)](https://dev.mysql.com/downloads/file/?id=480557)

`MySQL`其他教程相关请看: 
 - [易百教程](https://www.yiibai.com/mysql/)
 - [菜鸟教程](http://www.runoob.com/mysql/mysql-tutorial.html)
 - [廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001391435131816c6a377e100ec4d43b3fc9145f3bb8056000)

## 目录

  1. [Types](#types)
  1. [References](#references)
  1. [Objects](#objects)
  1. [Arrays](#arrays)
  1. [Destructuring](#destructuring)
  1. [Strings](#strings)
  1. [Functions](#functions)

## Types

  <a name="1.1"></a>
  <a name="types--primitives"></a>
  - [1.1](#types--primitives) 数据库的SQL语句操作
    + SQL (Structured Query Language)
    + DDL
    
         ```sql
         create database 库名
         create table [库名.]表名   use 库名

         drop database 库名
         drop table 表名
         ```
    + DML
    
         ```sql
         insert into users(id,name) values('1','zhangsan');
         update users set name='aa',age='18' where id='1';
         delete from 表名 where id='2';
         ```
    + DQL
    
         ```sql
         select * from 表名;
         ```
    + DCL

         ```sql
         \s   #看状态
         show databases;   #看所有库
         show tables;   #看所有表
         desc    #看表结构
         show variables  #配置文件变量
         ```

  <a name="1.2"></a>
  <a name="types--complex"></a>
  - [1.2](#types--complex)  执行SQL语句，连接到数据库服务器
    + 连接本机的服务器
    
        ```sql
        mysql -h localhost -u root -p
        ```
    + 通过地址连接到远端服务器
    
        ```sql
        mysql -h 192.168.x.x -u root -p
        ```
    + 通过域名连接到远端服务器
    
        ```sql
        mysql -h sicnu-it.cn -u root -p
        ```
    *mysql的默认端口是`3306`，可以编辑用户目录下的 `.my.cnf` 文件进行修改。`mysql -P 3306 -h sicnu-it.cn -u root -p`*

**[⬆ back to top](#目录)**

## References

  <a name="2.1"></a>
  <a name="types--primitives"></a>
  - [2.1](#types--primitives) xxxx
    + 查看当前自己信息
    
        ```mysql
        \s
        ```
    + 显示数据库文件的路径
    
        ```mysql
        show global variables like "%datadir%";
        ```
    + 退出
    
        ```mysql
        exit
        ```
    + 显示数据库列表
    
        ```mysql
        show databases;
        ```
    + 创建数据库
    
        ```mysql
        create database dbname;

        #避免已存在
        create database if not exists dbname;
        ```
    + 删除数据库
    
        ```mysql
        drop database dbname;

        #避免不存在
        drop database if exists dbname;
        ```
    + 选择一个库做为默认的数据库
    
        ```mysql
        use dbname;
        ```

