# MySQLBDB
## Day01
### 数据库基本概念
1.英文：（DtaBase-DB）
2.什么是数据库：用于存储和管理数据的仓库
3.特点：持久化存储数据，是一个文件系统；方便存储和管理数据；使用了统一的方式操作数据库（SQL）。
3.常见的数据库软件
### MySQL
1.登录mysql -u root -p root

### SQL
1.什么是SQL：结构化查询语言，其实就是定义了操作所有关系型数据库的规则。<br>
2.SQL的通用语法：SQL语句可以单行或多行书写，以分号结尾，可以使用空格或者缩进增加可读性；数据库不区分大小写，但是关键字推荐用大写；三种注释：--，#，/* */。<br>
3.SQL分类：DDL（操作数据库、表），DML（增删改表中的数据）、DQL（查询表中数据）、DCL（授权）<br>
### DDL：操作数据库、表
#### 操作数据库：CRUD（create、retrieve、update、delete、增删改查）
1.查询(Retrieve)：<br>
查询所有数据库的名称：SHOW DATABASES; --information_scheme放试图，mysql放核心数据<br>
查询某个数据库的字符集：查询某个数据库的创建语句 SHOW CREATE DATABASE mysql;<br>
2.创建（Create）：<br>
CREATE DATABASE DB1;<br>
CREATE DATABASE IF NOT EXISTS DB2；--如果存在数据库不创建，不存在创建<br>
CREATE DATABASE DB3 CHARACTER SET GBK;--制定字符集为GBK<br>
CREATE DATABASE IF NOT EXISTS DB4 CHARACTER SET GBK;--创建DB4数据库，判断是否存在，并制定字符集为GBK<br>
3.修改（Update）：<br>
ALTER DATABASE DB3 CHARACTER SET UTF8;--修改数据库的字符集<br>
4.删除（Delete）：<br>
DROP DATABASE DB3;--删除数据库<br>
DROP DATABASE IF EXISTS DB4;--如果存在数据库不删除，不存在删除<br>
5.使用数据库<br>
SELECT DATABASE();--查询当前使用的数据库名称<br>
USE DB1；--使用DB1数据库<br>
            
#### 操作表
1.查询(Retrieve)：<br>
USE MYSQL；<br>
SHOW TABLES; --查询某个数据库中所有的表名称<br>
DESC DB; --查询表结构<br>
查询某个数据库的字符集：查询某个数据库的创建语句 SHOW CREATE DATABASE mysql;<br>
2.创建（Create）：<br>
CREATE TABLE 表明{<br>
    列名1 数据类型1，<br>
    列名2 数据类型2，<br>
    ....<br>
    列名n 数据类型n<br>
    }；--最后一列不要加逗号<br>
数据库类型：整型：age int，浮点型：scource double(5,2),data：yyyy--MM--dd，datatime：yyyy-MM-dd HH:mm:ss,timestamp:yyyy-MM-dd HH:mm:ss,如果将来不给这个字段赋值，或赋值为null，则默认使用当前的系统时间，来自动赋值，varchar：name varchar(20)，最大20个字符，zhangsan，8个字符。<br>
CREATE TABLE STUDENT(<br>
    ID INT,<br>
    NAME VARCHAR(32),<br>
    AGE INT,<br>
    SCORE DOUBLE(4,1),<br>
    BIRTHDAY DATE,<br>
    INSERT_TIME TIMESTAMP<br>
);<br>
CREATE TABLE STU LIKE STUDENT;--复制表<br>
3.修改（Update）：<br>
ALTER TABLE 表名 RENAME TO 新表名; --ALTER TABLE STUDENT RENAME TO STU;--修改表名<br>
ALTER TABLE STU CHARACTER SET 新字符集类型；--ALTER TABLE STU CHARACTER SET UTF8/GBK;--修改表的字符集属性<br>
ALTER TABLE 表名 ADD 属性 属性类型；--ALTER TABLE STU ADD GENDER VARCHAR(10);--增加表的属性<br>
ALTER TABLE 表名 CHANGE 属性 新属性 新类型； -- ALTER TABLE STU CHANGE GENDER SEX VARCHAR(20);--修改表的属性名和类型<br>
ALTER TABLE 表名 MODIFY 属性 新属性；-- ALTER TABLE STU MODIFY SEX VARCHAR(10); --只修改表的属性名<br>
ALTER TABLE 表名 DROP 属性；-- ALTER TABLE STU DROP SEX;<br>
4.删除（Delete）：<br>
DROP TABLE 表名;--删除数据库<br>
DROP TABLE IF EXISTS 表名;--如果存在数据库不删除，不存在删除<br>
