**视图**：

当数据库部分内容需要用户不可见时，可以建立视图供用户查询。

```mysql
// 建立视图
create view faculty as select ID,name,dept_name from instructor;
```



**事务**：

原子性



**完整性约束**：

```mysql
// not null
name varchar(20) not null

// unique (在关系中没有两个元组能在列出的属性上取值相同)
unique (A1,A2,...,An)

// check
check (semester in ('Fall','Winter','Spring','Summer'));
```



参照完整性：

```mysql
// 外码
foreign key (A) references table;

// 更新、删除保持一致，见SQL.md
on delete cascade
on update cascade
```



**断言**：

```mysql
create assertion credit_earned_constraint check 
(not exists (select ID from student where tot_cred <> 
           (select sum(credits) from takes natural join course
           where student.ID = takes.ID
           and grade is not null and grade <> 'F')));
```



**SQL数据类型与模式**：

```mysql
// 时间
date '2001-04-25'
time '09:30:00'
timestamp '2001-04-25 10:29:01.45'

// 返回当前日期
current_date

// 返回当前时间（带时区）
current_time

// 返回当前的本地时间（不带时区）
localtime

// 返回当前的时间戳（带时区）
current_timestamp

// 返回当前的时间戳（不带时区）
localtimestamp

// 字符串转换
cast e as t

// 默认值 default
tot_cred numeric(3,0) default 0

// 创建索引
create index studentID_index on student(ID);

// 大对象
book_review clob(10KB)
image blob(10MB)

// 用户定义类型
create type Dollars as numeric(12,2) final;
create type Pounds as numeric(12,2) final;

// 创建与某个表模式相同的表
create table temp_instructor like instructor;

// 将查询的结果储存在新表里
create table tl as 
(selet * from instructor where dept_name = 'Music')
with data;

// 创建模式
create schema

// 删除模式
drop schema
```



**授权**：

```mysql
// 授予权限
grant select on department to Amit,Satoshi;
grant update (budget) on department to Amit,Satoshi;

// 收回权限
revoke select on department from Amit,Satoshi;
revoke update (budget) on department from Amit,Satoshi;
```



**角色**：

```mysql

```

