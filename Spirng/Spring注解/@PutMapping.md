用法与PostMapping一样
但是由于HTTP幂等性（要求重复请求资源无副作用）
*比如数据库查询操作*

**插入新数据使用@PostMapping
更新数据库用put**

put、get、delete都具有幂等性
post本身为非幂等请求
