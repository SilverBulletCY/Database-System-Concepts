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
