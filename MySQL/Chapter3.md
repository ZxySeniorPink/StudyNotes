# Chapter3 基本的select语句

## 1. SQL的分类

### DDL数据定义语言

DDL：Data Definition Languages

CREATE \ ALTER \ DROP（删除结构） \ RENAME \ TRUNCATE（清空）

### DML数据操作语言

DML：Data Manipulation Language

INSERT \ DELETE（删除一条记录） \ UPDATE \ `SELECT（DQL）`

### DCL数据控制语言 

DCL：Data Control Language

`COMMIT（提交） \ ROLLBACK（回滚到上一次提交）(TCL：Transaction Control Language)` \ SAVEPOINT（可以回滚到保存点） \ GRANT（给予权限）\ REVOKE（收回权限）

## 2. SQL语言的规则与规范

### 2.1 SQL语言的规则 — 必须遵守

- SQL可以写在一行或多行。为了提高可读性，各个子句分开写，必要时使用缩进
- 每条命令以 ; 或 \g 或 \G 结束
- 关键字不能被缩写也不能分行
- 关于标点符号
  - 必须保证所有的 () 、单引号、双引号是成对结束的
  - 必须使用英文状态下的半角输入方式
  - 字符串型和日期时间类型的数据可以使用单引号（' '）表示
  - 列的别名，尽量使用双引号（" "），而且不建议省略as

### 2.2 SQL的规范 — 建议遵守

- MySQL在Windows环境下是大小写不敏感的
- MySQL在Linux环境下是大小写敏感的
  - 数据库名、表名、表的别名、变量名是严格区分大小写的
  - 关键字、函数名、列名（字段名）、列的别名（字段的别名）是忽略大小写的
- 推荐采用统一的书写规范
  - 数据库名、表名、表别名、字段名、字段别名等都是小写
  - SQL关键字、函数名、绑定变量等都大写

### 2.3 注释

```sql
单行注释：#注释文字(MySQL特有的方式)
单行注释：-- 注释文字(--后面必须包含一个空格。)
多行注释：/* 注释文字 */
```

### 2.4 命名规则

- 数据库、表名不得超过30个字符，变量名限制为29个

- 必须只能包含A-Z，a-z，0-9，共63个字符

- 数据库名、表名、字段名等对象名中间不要包含空格

- 同一个MySQL软件中，数据库不能同名

  同一个库中，表不能重名

  同一个表中，字段不能重名

- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在SQL语句中使用`（着重号）引起来

- 保持字段名和类型的一致性，在命名字段并且为制定数据类型的时候一定要保证一致性。假如数据类型在一个表里是整数，那在另一个表里可就编程字符型了

### 2.5 数据导入指令

在命令行客户端登录mysql，使用source指令导入

```shell
mysql> source d:\mysqldb.sql
```

通过FOREIGN_KEY_CHECKS解决，用法如下

```sql
set FOREIGN_KEY_CHECKS=0;  #在导入前设置为不检查外键约束
set FOREIGN_KEY_CHECKS=1;  #在导入后恢复检查外键约束
```





























