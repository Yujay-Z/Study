#mysql的mac基本使用

mysql路径:
PATH="$PATH":/usr/local/mysql/bin


###1、启动、重启、停止、查看 MySQL状态
sudo /usr/local/mysql/support-files/mysql.server start

sudo /usr/local/mysql/support-files/mysql.server stop

sudo /usr/local/mysql/support-files/mysql.server restart

sudo /usr/local/mysql/support-files/mysql.server status

###2、重置密码
长时间不用，忘记密码是经常的事。。。此时需要重置密码。

mysql -u root -p

##3.进入数据库

/usr/local/MySQL/bin/mysql -u root -p

###4.查询数据库

show databases;

#二、连接远程数据库并进入命令行：

假设远程主机的IP为：ip地址，用户名为root,密码为123456

1、打开终端，输入如下命令：

mysql -h ip地址 -u root -p 123456

2、输入密码：

界面提示输入密码：

Enter password:

若为初次使用该数据库，则默认密码为空，直接回车即可进入mysql命令行；

若已设置密码，则输入密码后，回车，即可进入mysql命令行。

##三、退出命令：exit，再回车即可退出mysql命令行。

##四：

1、创建一个名字为NickYang数据库 create database NickYang character set utf8;

2、修改数据库编码：alter database NickYang character set utf8;

3、查看数据库是否创建成功：show databases;

4、进入数据库：use NickYang;

5、创建表并为表分配一个主键：create table yang(id int primary key);

6、查看表是否创建成功：show tables;

7、查看表结构：desc 表名;

8、增加字段：alter table 表名 add 字段名 数据类型[位置];

alter  table yang add  name varchar(255) after id;

9、删除字段：alter table 表名 drop 字段名;

alter table yang drop name;

10、新增数据：insert into 表名(字段名) values(值)

insert into  yang(id,name)  values(1,'name');

11、删除数据：delete from 表名 [where 条件];

delete from yang [where id = 1]

12、修改数据：update 表名 set 字段 = 值[where 条件]

update yang set name = 'yang' where id = 1;

13、查找数据：select * from 表名 [where 条件];

select * from yang [where id = 1];
