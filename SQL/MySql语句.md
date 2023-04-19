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
floor()
```
