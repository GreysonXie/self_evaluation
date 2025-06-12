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

### **学习路径**： 

关系数据库（英文定义）→关系（元组的集合）→关系`模式schema`和关系实例→`key`,`super key`,`candidate key`,`primary key`，外码→关系代数

#### 引申学习评估：

1.元组在table中如何体现：类似于excel中的一行记录

2.关系schema在数据库中的长什么样:例如instructor(id,name,dept_name,salary)

3.能够结合实例区分和把握各类别key，并能够找到并区分超码、候选码；另外：笛卡尔乘积拓展了解。

4.关系运算中选择（select）、投影（project）、and or not 、连接（join）、交并差等组合写法和符号掌握，注意关系代数在后续的sql代码编写中十分重要。

注意：需要熟悉并掌握markdown的写法

## 第四周 ##

### **学习路径**：

基本数据类型→2.基本模式→3.在schema定义中使用这些来规定属性→4.创建和删除表、清空数据→5.利用课上习题练习DML→6.多表查询：表与表的连接→附加操作

#### 评估：

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

### **学习路径**：

学习在datagrip从登录到连接数据库，并搭建好环境（注意SQL SHELL中的操作）→导入数据并配置源→运行sql文件→尝试SQL基本操作

#### 评估：能做到基本语句的撰写和判断错误

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

#### **回顾评估**：

1.join语句，写了join必须要写on

```sql
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
```sql
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

注意：前几周我们学的是初级`SQL`，学完后需要对自己的状况进行评估，若基础掌握不扎实，需要回头多看看。这以后我们学习的是中级SQL。
### **评估**： 

一些基础指令还不不能融会贯通，一旦题目的限制约束多了就需要借助AI来解答，因此此时我的基础并不牢固，需要再回头巩固。

### **学习路径回顾**：视图查询与更新---->事务（见中文版书P76）---->高效查找---->自定义函数---->授权---->

#### 学习注意：

1.为使得查询指令简洁，长属性名和table名可以利用rename as，

2.自定义数据类型或者函数的掌握，参考python的函数建立，

3.pg_dump和uv等的使用需要自己去拓展加深了解对于期末项目有帮助。

## **课后项目学习评估**： 通过借助AI，独自完成了智能家居系统的fastapi的页面创建。总结如下：

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


## 第10周 ##

### **学习路径**：

设计数据库---->重点掌握E-R图的设计和画法---->映射基数（包括：基数约束）---->实体集的主码（下划线）和联系集的主码---->E-R转为关系模式---->去除冗余模式及模式的合并

#### 学习重点和个人总结：

1.E-R图能够最直观的体现数据库设计中各个实体集（table）的关系；注意画图时实体集用圆角方框，关系用菱形（diamond），关系也能拥有的属性——描述性属性（也就是所属性既能来自于实体也能来自于联系）；

2.对于关系模型和E-R之间的关系不太领会，还需要自己进一步去搜资料学习。

3.派生属性本身就可以通过实体集的属性之间的关联推算出来，所以也就没有存储的必要。

4，关系和实体之间连线的有箭头一侧代表one，没有箭头一侧则代表many。画图时要体现出这个还是需要多想想。我还不能熟练画出E-R；有两条线的一侧则代表实体全参与。

5.需要掌握至少一种画图工具，例如：在线画图网页draw.io。draw.io个人使用感觉太卡了，而且图形模板选项有限，可以再试试其他画图工具，lucidchart或者专业画图工具（ERwin,microsoft visio）

6.datagrip的而可视化方法需要掌握

7.联系集的超码判定我还是优点不熟悉；注意many to many时的两边的主码必须同时选。

8.注意弱实体集的画法（其主码下面应用虚线），包括与其连接的关系集，线条和其本身的图形都要变为双线；注意判断弱实体集，很容易出错。

9.注意在画E-R图时并不是简单的将实体及其属性写上去，需要把握实体之间的联系，尤其是去除冗余属性。

10.习题参考中文版P179

11.对于联系集的主码的确定需要谨慎，我还没有完全掌握。

12.什么时冗余模式，例如：连接弱实体集和其所依赖的强实体集的模式冗余的，

13.one-to-one的联系因该可以合并，我觉得只需要将一侧的主码计入到另一侧就可以。



## 第11-12周 ##

### **学习主题**：关系数据库范式————无损分解是好的关系数据库设计的基础

### 学习路径：

大小模式的区别---->无损分解---->几大范式（尤其是BCNF）---->平凡依赖、依赖闭包

#### 学习回顾评估：

1.听的第一遍还是不太能判断哪些符合BCNF,再借助AI辅导和做课后习题下大致掌握了判断技巧，但是对于得出所有的非平凡实体集需要注意，一些非平凡实体集α→β的α可以通过与其他属性结合从而构成新的非平凡实体集，所以需要谨慎。
最开始由于对*平凡函数*依赖（AB->A,AB->B即母集推出子集）理解不够，所以判断失误。

`BCNF`

具有函数依赖集F的关系模式R属于BCNF的条件是,对 $F^+$中所有形如α→β的函数依赖,下面至少一个成立:

- α→β是平凡的函数依赖
- α是R的一个超码

2.大模式存在数据重复的问题，所以需要分解，但是随意分解很容易造成信息损失，因此因此BCNF的出现为分解提供了很好的准则————无损分解。

3.符合规范（normal）的东西即为好 —— good form

4.模式分解还是把握不到位。


## 第13-14周 ##

### 主题：实现数据库

### 学习路径：

python与数据库的连接通过python---->环境的配置和在python执行指令实现数据的增和删---->数据库存储


#### 学习评估：

1.简洁方便的方法是直接使用pycharm创建项目。直接配好环境，安装相关的包：psycopg[binary]、psycopg2-binary。

```python
import psycopg
from sqlalchemy.orm import Session#我自己来连接数据库使用的sqlalchemy，这个复杂一些。
# Update the conn as you need
with psycopg.connect("dbname=mydb user=postgres port=5432 password=213108") as conn:
    with conn.cursor() as cur:
        cur.execute("SELECT * FROM department")
        records = cur.fetchall()
        print(records)
```
2.数据库存储的知识做了解。

3.把握PGSQL的page的内容组织、page与page之间组织

4.page layout得分页槽结构比较有意思。

5.存储模型：行存储和列存储。能够对什么时候用什么存储模型有一个基本的判断。

6.metadata展示的是数据得信息，在期末项目得第一个项目里可能用得到，可以尝试了解




## 第15周 ##

### 学习主题：索引和查询计划

#### 学习路径：

有序索引---->聚集和非聚集---->稠密和稀疏索引---->重点：B+tree的理解和使用---->哈希索引（无序，直接找到目标）---->PG默认创建非聚集索引

#### 学习回顾：

1.有序的包含聚集和非聚集索引，一般来说创建非聚集索引，成本较低。（二分查找可以提高查找速度）

2.聚集和非聚集index的区别在于，前者的顺序与文件记录顺序一致，后者不一致。注意：一表只能有一个聚集索引，但可以有多个非聚集索引。

3.稠密即一个萝卜一个坑，每一个元组都有一个index；稀疏就是只有部分的tuple有index。稀疏索引只能是聚集索引，因为若为非聚集索引则可能无法完成搜索。

  而这对比，dense index能够精准定位，但是文件开销大；而稀疏index相对较慢，但文件开销小。

Btree（平衡的）；根节点，叶节点，parent节点和child节点。特殊的二叉树：每一个node只能由2个分支，搜索复杂度为logN。

Btree的每一个node 可以有多个key，这也就意味着，data量一定的情况下，tree会更矮，search会更快。

在Btree中最多访问4或5个page即可找到目标（即tree最多有4或者5层）。

非叶子节点的孩子数在n/2~n之间

4.N=1000000(记录数)，n=100（孩子数）,最多访问log_n/2(N)个节点

5.重点掌握tuple的对比，例如：现有索引（a,b），比较时，看第一个位置a，若第一个可以比，则确定顺序；若第一个相同，则比较第二个位置b。

'%b'不可以比，因为%未知，'a%'可以比，因为开头处a可以知道。

6.hash只能处理相等情况。index rate=1.若两个hash可以索引到同一个位置，则产生冲突，需要冲突消解。

7.PG中索引代码示例：

```sql
SELECT indexname, indexdef
FROM pg_indexes
WHERE tablename = 'student';
```
student_pkey
CREATE UNIQUE INDEX student_pkey
ON public.student USING btree (id)
```sql
SELECT
 indexname,
 pg_relation_filepath(indexname::regclass) as file_path
FROM pg_indexes
WHERE tablename = 'student';
```

8.索引不一定提高查询性能，例如在数据量较少时，即基数小不适合建立index。

9.
```sql
EXPLAIN ANALYSE
SELECT * FROM instructor
WHERE id = '33456';
```
查看语句运行，使用索引来查找
```sql
EXPLAIN ANALYSE
SELECT * FROM instructor
WHERE name = 'Gold';
```
使用扫描来查找
```sql
CREATE TABLE test_index(
id int,
name varchar(100)
);
```
创建表
```sql
INSERT INTO test_index(id, name)
(SELECT generate_series(0, 1000000),
gen_random_uuid());
```
生成数据
```sql
EXPLAIN ANALYZE SELECT * FROM test_index
WHERE id BETWEEN 100 AND 500;
```
查询内容，并行查找。
```sql
CREATE INDEX id_idx ON test_index(id);
```
创建索引来再查找，速度快了很多，若采用ahsh index，则速度很慢，因为data量很大，还不如用scan。

10.page过多时，可以基于page再建page。

11.执行查询计划之前会受到optimizer的影响，尽可能先执行σ（选择）。

#### 评估：

1.对于hash index，我还是没有把握，什么时候该用hash和什么时候用有序index。

2.对于tuple对比，的几个习题，自己做的时候不太懂，讲解以后才把握到一些，需要进一步学习。

3.对于index的一些基本特征基本了解了。


## 第16周 ##

###学习评估：

1.对于DuckDB的优点和使用方式基本了解，感觉是一个python+SQL的结合体，克服了python无法高效读取过大文件的缺陷，效率更高，是处理大数据的好工具

2.duckDB的语法结构基本沿袭了PG，且使用方便，UI页面很好用。

3.《duckDB in action》参考书目

4.拓展的slidev、papuet都可以进一步了解。

5.vector DB，是现在很流行的DB，在我们过往的数据分析中其实很多都应用到其中的原理，可以迁移学习理解。尝试用PG中的向量DB插件看看效果。








