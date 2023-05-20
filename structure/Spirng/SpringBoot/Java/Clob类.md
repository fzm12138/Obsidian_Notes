CLOB 数据类型与 TEXT 数据类型类似，但 CLOB 数据类型具有下列优点：

-   应用程序可以读写 CLOB 对象的任何部分。
-   由于应用程序可以访问 CLOB 对象的任何部分，所以访问速度可以快很多。
-   缺省特征相对易于覆盖。数据库管理员能够在列级别覆盖智能大对象空间的缺省特征。应用程序员可以在创建 CLOB 对象时覆盖列的某些缺省特征。
-   可以使用等于运算符 (=) 来测试两个 CLOB 值是否相等。
-   CLOB 对象在发生系统故障时是可恢复的，并且在 DBA 或应用程序员指定了事务隔离方式的情况下遵守该方式。（CLOB 对象的恢复要求数据库系统有必需的资源以提供足够大的缓冲区来处理 CLOB 对象。）
-   可以使用 CLOB 数据类型来为用户定义的数据类型提供大存储空间。
-   DataBlade® 开发者可以对 CLOB 数据类型创建索引。

CLOB 数据类型的缺点如下：

-   在完整的磁盘页中分配它，因此短项浪费空间。
-   对您可以如何在 SQL 语句中使用 CLOB 列有限制。（请参阅[使用智能大对象](https://www.ibm.com/docs/zh/SSGU8G_12.1.0/com.ibm.ddi.doc/ids_ddi_113.htm)。）
-   它对所有 IBM Informix 数据库服务器都不可用。
在任何 SQL 语句中（无论是交互式的还是编程的），都不能在以下上下文中使用 BLOB 或 CLOB 列：

-   在算术或布尔表达式中
-   在 GROUP BY 或 ORDER BY 子句中
-   在 LIKE 或 MATCHES 条件中
-   在 UNIQUE 测试中
-   用于建立索引，作为 IBM Informix B 型树索引的一部分
    
    然而，DataBlade® 开发者可以对 CLOB 列创建索引。
    

在以交互方式输入的 SELECT 语句中，BLOB 或 CLOB 列可以：

-   在创建表时通过 DEFAULT NULL 子句将 NULL 值指定为缺省值
-   在创建表时使用 NOT NULL 约束来拒绝 NULL 值
-   使用 IS [NOT] NULL 谓词进行测试