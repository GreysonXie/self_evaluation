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

1.numeric、int、char、varchar、decimal、float。其中decimal的独特之处。

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
另：
1.模糊查询的like语句以及字符的匹配操作、转义字符\有哪些、如何进行值的拼接||。

2.作业总结：对于psql的运用
首先需要进入是输入密码
其次通过\l、\dt查看所有的库及表
通过\c university切换到university库并进行操作

## 第五周 ##

学习在datagrip从登录到连接数据库，并搭建好环境（注意SQL SHELL中的操作）→导入数据并配置源→运行sql文件→尝试SQL基本操作

评估：能做到基本语句的撰写和判断错误

1.<>---!=

2.匹配字符% 、_

3.对于null（与false、true的交并，not null =null）、know、unknow的认知和理解

4.判定bool时应用is know和is unkown

5.coalesce的使用例如coalesce（salary，0）是将为空的salary变为0并输出

6.聚集函数 max 、min avg

7.where的合法性：其后的条件应该是一一比照的，而不能一对多，其后面不能用聚集函数

8.having后可以跟聚集函数，having一般结合group by使用，是基于group by进行筛选的

9.嵌套语句的使用，case end 语句要重点掌握；至少比某一个要大用'> some'、大于所有用'> ALL()';ORDER BY （RANDOM等） LIMIT + num的使用，

10.需要重点练习avg等聚合函数、group by等今日所学语句的合法性辨认。


## 第六至八周 ##

回顾评估：
1.join语句，写了join必须要写on

```
select *  
from student left join takes  
on student.id = takes.id; 

select *  
from student left join takes  
using(id);  
  
select *  
from student left join takes  
on true  
where student.id = takes.id;
```

2.on vs  where结果要一样就必须是自然连接

left join  right join用union结合两者来替代 full outer join

多表查询-- 自然连接-- join on/using( ...)-- 
```
SELECT *  
FROM student  
NATURAL LEFT JOIN takes;

select *  
from student left join takes  
on student.id = takes.id; 

二者时等价的
```
3.对于case语句的用法和写的位置不熟练，对于链接的概念还是有待进一步学习理解，

4.对于标量子语句不熟悉：什么是标量子语句

5.对于子查询结果较多时用exist查询而不建议用in，对于with建立临时关系的用法不太熟悉，但是感觉用途非常广泛
其例子如下：

```sql
with total(value,dept_name) as
    (select sum(salary),dept_name from instructor group by dept_name )
select dept_name,value
from total
where value = (select max(value) from total);
```

6.可以多多借助网站https://www.w3schools.com/sql/sql_join.asp 进行复习.对于time、timestamp及类型转换有很多需要用法，需要多加回顾和练习

7.创建角色与连接数据库需要掌握，在后面的大作业可能用到

8.补充：serial的使用，实现id自增

9.能够熟练的完成table数据的插入和更新,删除，指令：incert into --() values ,update -- set --,delete from -- where。

10.行约束（写在旁边）和列约束（写在后面），对于check指令的使用基本了解

11.对于主表和从表，外码之间的关联可以借助删除引发的连锁效应来把握。

12.SQL中用rank() over(--)


## 第九周 ##

注意：前几周我们学的是初级`SQL`，学完后需要对自己的状况进行评估，若基础掌握不扎实，需要回头多看看。
**评估**： 一些基础指令还不不能融会贯通，一旦题目的限制约束多了就需要借助AI来解答，因此此时我的基础并不牢固，需要再回头巩固。

*学习路径回顾*：视图查询与更新---->事务（见中文版书P76）---->高效查找---->自定义函数---->授权---->

学习注意：

1.为使得查询指令简洁，长属性名和table名可以利用rename as，

2.自定义数据类型或者函数的掌握，参考python的函数建立，

3.pg_dump和uv等的使用需要自己去拓展加深了解对于期末项目有帮助。

*课后项目学习评估*： 通过借助AI，独自完成了智能家居系统的fastapi的页面创建。总结如下：

1.需要给AI说清楚你所会的技能和软件是什么，如我掌握了python和SQL的基础语法，常用软件为pycharm和datagrip，pgsql。

2.点明你的学习目标和可利用的额外工具：搭建智能家居系统，借助fastapi等和python相关的包

3.如果自己对于完成任务的步骤不熟悉则需要向AI说明：希望可以从头到尾一步步教导我完成任务。

4.完成总结：
    
    能够实现python中与数据库的连接（包括用什么包如何确定路径等，特别注意此处可能需要涉及到环境变量的配置）；
    借助alchemy等python包实现fastapi的接口搭建两类POST和GET；
    进入fastspi界面一般需要在终端输入：
   `````python
   uvicorn main:app --reload
   `````
    在浏览器进入网址：http://localhost:8000/docs
    利用python的可视化在fastapi端口完成绘图；
    利用LLM或者NLP模型将用户的需求转化为SQL语言从数据库中提取数据；
    当页面不随着代码的变化而改变时，只需要：1.关掉窗口或者浏览器  2，重启并重新跑一遍代码 3.重启电脑







