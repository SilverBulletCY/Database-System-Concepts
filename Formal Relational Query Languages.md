**关系代数**：

选择：$\sigma$
$$
\sigma_{depy\_name="Physics" \land salary > 90000}(instructor)
$$
投影：$\Pi$
$$
\Pi_{ID,name,salary}(instructor)
$$
并运算：
$$
\Pi_{course\_id}(\sigma_{semester="Fall" \land year=2009}(section)) \cup 
\Pi_{course\_id}(\sigma_{semester="Spring" \land year=2010}(section))
$$
集合差运算：
$$
\Pi_{course\_id}(\sigma_{semester="Fall" \land year=2009}(section)) - 
\Pi_{course\_id}(\sigma_{semester="Spring" \land year=2010}(section))
$$
笛卡尔积运算：
$$
\sigma_{dept\_name="Physics"}(instructor \times teaches)
$$
更名运算：
$$
\Pi_{instructor.salary}(\sigma_{instructor.salary < d.salary}(instructor \times 
\rho_{d}(instructor)))
$$

集合交运算：
$$
\Pi_{course\_id}(\sigma_{semester="Fall"\land year=2009}(section)) \cap
\Pi_{course\_id}(\sigma_{semester="Spring"\land year=2010(section)})
$$
自然连接运算：
$$
\Pi_{name,course\_id}(instructor \bowtie teaches)
$$
赋值运算：
$$
temp1\leftarrow R\times S
$$
外连接运算：

1. 左外连接：⟕
2. 右外连接：⟖
3. 全外连接：⟗

聚集运算：
$$
\mathcal{G}_{\textbf {sum}(salary)}(instructor)
$$