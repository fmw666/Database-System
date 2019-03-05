# 数据库系统
&emsp;&emsp;*数据库系统（Database System，DBS），是由数据库及其管理软件组成的系统。它是为适应数据处理的需要而发展起来的一种较为理想的数据处理的核心机构。它是一个实际可运行的存储、维护和应用系统提供数据的软件系统，是存储介质、处理对象和管理系统的集合体。*

<div align="center">
    <img src="pics/donman.jpg" width=200px>
</div>

## 目录
  1. [关系数据库及标准语言SQL](#1)
  
  2. [xx](#2)

<a name="1"></a>
## 关系数据库及标准语言SQL
&emsp;&emsp;🛢 **结构化查询语言（Structured Query Language， SQL）** 是关系数据库的标准语言，也是一个通用的、功能极强的关系数据库语言。其功能不仅仅是查询，而是包括数据库模式创建、数据库数据的插入与修改、数据库安全性完整性定义与控制等一系列功能。

<div align="center">
    <img src="pics/cute-tuicheche.jpg" width=150px>
</div>

### SQL 的产生与发展
&emsp;&emsp;🗓 SQL 是在1974年由 Boyce 和 Chamberlin 提出的，最初叫 Sequel。

### SQL 的特点
&emsp;&emsp;💡 SQL 之所以能够为用户和业界所接受并成为国际标准，是因为它是一个综合的、功能极强同时又简洁易学的语言。SQL 集数据查询（data query）、数据操纵（data manipulation）、数据定义（data definition）和数据控制（data control）功能于一体。

&emsp;&emsp;💡 SQL 功能极强，由于设计巧妙，语言十分简洁，完成核心功能只用了9个动词，SQL 接近英语口语，因此易于学习和使用。

|SQL 功能|动词|
|:-----:|:---|
|数据查询|SELECT|
|数据定义|CREATE，DROP，ALTER|
|数据操纵|INSERT，UPDATE，DELETE|
|数据控制|GRANT，REVOKE|

### 例：学生-课程数据库
&emsp;&emsp;📃 我们以学生-课程数据库为例来体现 SQL 的数据定义、数据操纵、数据查询和数据控制语句。在学生-课程数据库中包括以下三个表：

+ [学生表](#student)： Student(Sno,Sname,Ssex,Sage,Sdept)
+ [课程表](#course)： Course(Cno,Cname,Ccredit)
+ [学生选课表](#sc)： SC(Sno,Cno,Grade)

<a name="student"></a>
***Student表：***

|学号<br>Sno|姓名<br>Sname|性别<br>Ssex|年龄<br>Sage|所在系<br>Sdept|
|:---------:|:----------:|:----------:|:----------:|:------------:|
|2017110110|范茂伟|男|20|CS|
|2017110131|李云祥|男|21|CS|
|2017120518|王敏|女|19|IS|

<a name="course"></a>
***Course表：***

|课程号<br>Cno|课程名<br>Cname|学分<br>Ccredit|
|:----------:|:-------------:|:-------------:|
|1|数据库|4|
|2|高等数学|5|
|3|数据结构|4|
|4|操作系统|2|

<a name="sc"></a>
***SC表：***

|学号<br>Sno|课程号<br>Cno|成绩<br>Grade|
|:--------:|:-----------:|:-----------:|
|2017110110|1|92|
|2017110110|2|86|
|2017110110|3|88|
|2017110131|2|90|
|2017110131|3|84|

<div align="center">
    <img src="pics/xiaoren.gif" width=50px>
</div>

#### 基本表的定义、删除与修改
```sql
/* SQL 语言使用 CREATE TABLE 语句定义基本表（不区分大小写），其基本格式为：
    CREATE TABLE <表名> (<列名><数据类型> [列级完整性约束条件],
                         <列名><数据类型> [列级完整性约束条件],
                         ...
                         [表级完整性约束条件]
    );
*/
/* 建立一个"学生表Student" */
CREATE TABLE Student(
    Sno CHAR(10) PRIMARY KEY,    /* 列级完整性约束条件，Sno是主键 */
    Sname CHAR(20) UNIQUE,       /* Sname 取唯一值 */
    Ssex bit,                    /* 用布尔类型，01表示男女 */
    Sage SMALLINT,
    Sdept CHAR(20)
);
```
