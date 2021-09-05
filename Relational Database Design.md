**第一范式（1NF）**：保证原子性，不以集合、序列作为属性存在。

解决方法：将序列拆分。

**第二范式（2NF）**：消除非主属性对于主属性的部分依赖。

解决方法：根据部分依赖拆分表。

**第三范式（3NF）**：消除非主属性对于主属性的传递依赖。

解决方法：根据传递依赖拆分表。

**巴斯范式（BCNF）**：消除主属性对主键的部分依赖与传递依赖。

解决方法：根据部分依赖与传递依赖拆分表。

**第四范式（4NF）**：消除多值依赖。

解决方法：实现“一对一”关系。



ref:https://blog.csdn.net/atd_nian/article/details/3917931?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_v2~rank_aggregation-1-3917931.pc_agg_rank_aggregation&utm_term=%E5%87%BD%E6%95%B0%E4%BE%9D%E8%B5%96%E5%85%B3%E7%B3%BB%E7%9A%84%E4%BE%8B%E5%AD%90&spm=1000.2123.3001.4430

ref:https://blog.csdn.net/sumaliqinghua/article/details/85872446#commentBox

例：关系模式R(x,y,z)，满足函数依赖集f={x->y,x->z}，求R最高为第几范式。

![image-20210905215801509](C:\Users\戴尔\AppData\Roaming\Typora\typora-user-images\image-20210905215801509.png)

首先，可以确定x既为候选码，也为主码。x为主属性，y,z为非主属性。

因为左边只有x，所以没有非主属性对于主属性的部分依赖。

也可知，没有y->z或z->y，所以也没有非主属性对于主属性的传递依赖。

因为没有x->x，所以没有主属性对主键的部分依赖与传递依赖。

但是x->y,x->z是一对多的关系，所以不符合4NF。

因此R最高满足BCNF。



几个例子：https://blog.csdn.net/weixin_43941364/article/details/106143475?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_v2~rank_aggregation-7-106143475.pc_agg_rank_aggregation&utm_term=%E5%87%BD%E6%95%B0%E4%BE%9D%E8%B5%96%E5%85%B3%E7%B3%BB%E7%9A%84%E4%BE%8B%E5%AD%90&spm=1000.2123.3001.4430

解题方法：

![image-20210905223517846](C:\Users\戴尔\AppData\Roaming\Typora\typora-user-images\image-20210905223517846.png)