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

