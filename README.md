# MySQLBDB
## Day01
### 数据库基本概念
1.英文：（DtaBase-DB）
2.什么是数据库：用于存储和管理数据的仓库
3.特点：持久化存储数据，是一个文件系统；方便存储和管理数据；使用了统一的方式操作数据库（SQL）。
3.常见的数据库软件
### MySQL
1.登录mysql -uroot -proot

### SQL
1.什么是SQL：结构化查询语言，其实就是定义了操作所有关系型数据库的规则。
2.SQL的通用语法：SQL语句可以单行或多行书写，以分号结尾，可以使用空格或者缩进增加可读性；数据库不区分大小写，但是关键字推荐用大写；三种注释：--，#，/* */。
3.SQL分类：DDL（操作数据库、表），DML（增删改表中的数据）、DQL（查询表中数据）、DCL（授权）
### DDL：操作数据库、表
#### 操作数据库：CRUD（create、retrieve、update、delete、增删改查）
1.查询(Retrieve)：
查询所有数据库的名称：SHOW DATABASES; --information_scheme放试图，mysql放核心数据
查询某个数据库的字符集：查询某个数据库的创建语句 SHOW CREATE DATABASE mysql;
2.创建（Create）：
CREATE DATABASE DB1;
CREATE DATABASE IF NOT EXISTS DB2；--如果存在数据库不创建，不存在创建
CREATE DATABASE DB3 CHARACTER SET GBK;--制定字符集为GBK
CREATE DATABASE IF NOT EXISTS DB4 CHARACTER SET GBK;--创建DB4数据库，判断是否存在，并制定字符集为GBK
3.修改（Update）：
ALTER DATABASE DB3 CHARACTER SET UTF8;--修改数据库的字符集
4.删除（Delete）：
DROP DATABASE DB3;--删除数据库
DROP DATABASE IF EXISTS DB4;--如果存在数据库不删除，不存在删除
5.使用数据库
SELECT DATABASE();--查询当前使用的数据库名称
USE DB1；--使用DB1数据库
            
#### 操作表
1.查询(Retrieve)：
查询所有数据库的名称：SHOW DATABASES; --information_scheme放试图，mysql放核心数据
查询某个数据库的字符集：查询某个数据库的创建语句 SHOW CREATE DATABASE mysql;
2.创建（Create）：
CREATE DATABASE DB1;
CREATE DATABASE IF NOT EXISTS DB2；--如果存在数据库不创建，不存在创建
CREATE DATABASE DB3 CHARACTER SET GBK;--制定字符集为GBK
CREATE DATABASE IF NOT EXISTS DB4 CHARACTER SET GBK;--创建DB4数据库，判断是否存在，并制定字符集为GBK
3.修改（Update）：
ALTER DATABASE DB3 CHARACTER SET UTF8;--修改数据库的字符集
4.删除（Delete）：
DROP DATABASE DB3;--删除数据库
DROP DATABASE IF EXISTS DB4;--如果存在数据库不删除，不存在删除
