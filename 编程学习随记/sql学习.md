```sql
# sql对大小写不敏感
# sql以分号结尾;
show databases
# -- 单行注释
# # 我是注释
# 多行/*     */

# 查看数据库
show databases;

# 使用数据库
use 数据库名;

# 创建数据库
create database 数据库名;

# 删除数据库
drop database 数据库名;

# 查看当前使用的数据库
select database()

# 查看有哪些表
show tables;

# 删除表
drop table 表名称
drop table if exists 表名称

# 创建表
create table(
  id int,
  name varchar(23);
  day date
)
int
float
varchar
date
timestamp

# dml
student(
	id int;
)
# 插入insert 
insert into student(id) value(1),(2),(3);

# del
delete from student where id=1;
# 删掉id等于1的数

# updata 
update student set d =13 where id = 4;


# 数据查询
select id,age,name from student;
select * from student;
# 过滤
select from student where age > 20;

# dql
select gender,avg(age) from student group by gender;
# group by出现谁 select 才可以出现
# sum()
# avg()
# min()
# max()
# count(列｜*)


# 排序分页,desc降序
select * from student where age>20 order by age;

# 结果分页显示,limit 限制5条
select * from student limit 5;
# 第10条开始，显示5行
limit 10,5


# python操作mysql
import pymysql

db = pymysql.connect(
    host="localhost",
    port=3306,
    user='root',    #在这里输入用户名
    password='root',     #在这里输入密码
    charset='utf8mb4'
    ) #连接数据库

cursor = db.cursor() #创建游标对象

sql = 'show databases' #sql语句

cursor.execute(sql)  #执行sql语句

one = cursor.fetchone()  #获取一条数据
print('one:',one)

many = cursor.fetchmany(3) #获取指定条数的数据，不写默认为1
print('many:',many)

all = cursor.fetchall() #获取全部数据
print('all:',all)

cursor.close()
db.close()  #关闭数据库的连接


```

