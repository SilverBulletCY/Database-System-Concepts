**视图**：

当数据库部分内容需要用户不可见时，可以建立视图供用户查询。

```mysql
// 建立视图
create view faculty as select ID,name,dept_name from instructor;
```



**事务**：