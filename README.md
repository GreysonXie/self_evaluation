# self_evaluation
数据库课程学期自我评估

## 第一周 ##
根据自身偏好，借助CSDN等博客的指导正确下载并安装了PostgreSQL，pgadmin4，datagrip。

参考预习书籍：《database system concepts》,《数据库系统概念》

总结认为数据库是一门应用型的学科技能，需要借助AI来帮助自己理解基础命令和进阶学习，在学习的过程中借助`AI`给自己出题、自己回答后再用AI来修改是一个快速掌握基础的方法

## 第二周 ##

学会调用`api`接口完成挑战题，并在课上学习了数据库的关键概念：

学习并把握`data`,`databse`的定义和类型，了解了DBMS的基本类型，各自的优劣之处。

学习并尝试回答：数据库的应用范围；它与文件管理系统的区别与联系；文件管理系统的缺陷有哪些；`data model`有哪些，其中关系型数据库是本学期主要学习的内容，需要深入了解；什么是DDL,DML（本课重点）.

注意SQL是一种声明式语言，关注what而非how

通过广泛的查阅资料和博客学习并深入理解了**关系**一词在数据库的含义。


## 第三周 ##

关系数据库（英文定义）→关系（元组的集合）→关系`模式schema`和关系实例→`key`,`super key`,`candidate key`,`primary key`，外码→关系代数

引申学习评估：

1.元组在table中如何体现：类似于excel中的一行记录

2.关系schema在数据库中的长什么样:例如instructor(id,name,dept_name,salary)

3.能够结合实例区分和把握各类别key，并能够找到并区分超码、候选码；另外：笛卡尔乘积拓展了解。

4.关系运算中选择（select）、投影（project）、and or not 、连接（join）、交并差等组合写法和符号掌握，注意关系代数在后续的sql代码编写中十分重要。

注意：需要熟悉并掌握markdown的写法

## 第四周 ##

1.基本数据类型→2.基本模式→3.在schema定义中使用这些来规定属性→4.创建和删除表、清空数据→5.利用课上习题练习DML→6.多表查询：表与表的连接→附加操作

评估：

1.numeric、int、char、varchar、decimal、float。decimal的独特之处。

2.schema设定时建议用英文；半角英文和全角的区别，用用半角英文符；不区分大小写。

3.掌握在schema中设定主码和根据实际情况具体规范输入数据的类型。

4.create table、drop table、delete from。

5.select 、where、from基本查询结构的使用，其中去重复指令的使用didtinct用在select后面；!=,<>不等于符号的使用；between and与<=,>=符号的综合使用；多个条件匹配用行构造器

6.*用法，rename、order by + asc或desc。

注意：拓展了解，nul和unknown的用法
 ```sql
true and unknown is unknown

false and unknown is false

true or unknown is true

false or unknown is unknown

not unknown is unknown
```




