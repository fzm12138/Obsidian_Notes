- 聚合函数
```mysql
AVG：select avg (列名) from 表名
count <!--返回某字段行数-->
max <!--返回某字段最大值-->
min <!--返回某字段最小值-->
sum <!--返回某字段的和-->
```

- 字符串函数
```mysql
concat()<!--链接字符串s1,s2....sn为一个完整字符串-->
insert(s1,p1,n,news)<!--将串c1从p1位置开始，n个长度的字符串替换为news-->
lower(s) <!--全改为小写-->
uppper(s)<!--全改为大写-->
substring(s,num,len)<!--返回串s第num个位置开始的长度为len的字串-->
```

- 时间日期函数
```mysql
curdate();<!--获取当前日期-->
curtime();<!--获取当前时间-->
now();<!--获取当前日期和时间-->
week(date);<!--返回date为一年中的第几周-->
year(date);<!--返回日期为date的年份-->
hour(time);<!--返回time的小时值-->
minute(time);<!--返回time的分钟值-->
datediff(date1,date2);<!--返回日期参数(date1和date2间相隔的天数)-->
adddate(date,n);<!--date,n-->
```

- 数学函数
```mysql
ceil(x);<!--返回>=x的最小整数-->
floor(x);<!--返回<=x的最大整数-->
rand();<!--返回0~1之间的随机数-->
```

- oder by子句
  order子句按照一定顺序排列查询结果
	- asc升序排列，desc降序排列
- limit子句
	- 显示指定位置指定行数的记录
	- select字段名 列表 from表名 where 约束条件 group by 分组的字段名 order by排序列名 limit 位置偏移量,行数；
--------------------
- 模糊查询
	- in子查询not in 子查询使用in关键字可以使父查询匹配子查询返回多个字段值，解决使用比较运算符(=,>等),子查询返回值不唯一错误信息

- like模糊查询
```mysql 
like语句语法格式:
select *from 表名 where 字段名 like 对应值（字串）
它主要针对字符型字段，它的作用是在一个字符型字段列中检索包含对应字串的
```

A:%包含零个或多个字符的任意字符串:
```mysql
LIKE'Mc%' 将搜索以字母Mc开头的所有字符串
LIKE'%inger%' 将搜索以字母inger结尾的所有字符串
LIKE'%en%' 将搜索在任何位置包含字母en的字符串
LIKE'_heryl'将搜索以字母herly结尾的所有6个字母的名称
<!----- []指定范围([a-f])或集合([abcdef]中任何字符) ----->
LIKE'[CK]ars[eo]n'将搜索任何(C/K)ars(e/o)n形式的名称
LIKE'[M-Z]inger'将搜索以字符串inger结尾，以从M到Z的任何单个字母开头的所有名称，如Ringer
[^]不属于指定范围[a-f]或集合[abcdef]的任何单个字符
LIKE 'M[^c]%'将搜索以M开头，并且第二个字符表示c的所有名称
```



[MySQL数据库命令\_古哥199的博客-CSDN博客](https://blog.csdn.net/qq_42992643/article/details/82959720?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168188001016800222890840%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168188001016800222890840&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-82959720-null-null.142^v84^koosearch_v1,239^v2^insert_chatgpt&utm_term=mysql%E6%95%B0%E6%8D%AE%E5%BA%93%E5%91%BD%E4%BB%A4%E5%A4%A7%E5%85%A8&spm=1018.2226.3001.4187)


































