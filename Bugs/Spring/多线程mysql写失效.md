
多线程下写mysql失效，读不受影响
处理流程：
- 检查语法
- 查看数据库引擎
	- innodb
- 查看mysql隔离级别
	- Read-Repeatable
		- 它确保同一事务多个实例在并发read时，看到同样的data
		- (不能阻止幻读)
- 设置新的隔离级别
	- Read-Committed
	- set global transaction isolation level read committed
	- 一个事务只能看见已经提交事务所作的改变
	- 同一事务其他实例在该实例处理时可能有新的commit
	- 同一个select可能不同结果
###### 未成功
- 经检查，jpa提供的方法一律失效
- 尝试换成mybatis
Failed to create query for method public abstract xxx.xxx.xxxx
xxxx.xxRepository.saveById(int); No property 'saveById' found for type 'Fertilizer'
```kotlin
    implementation 'org.mybatis:mybatis:3.5.11'
    implementation 'org.mybatis:mybatis-spring:3.0.0'
    implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:3.0.0'

TODO("引入依赖")
```
**启动类加注解:**
```kotlin
@MapperScan(value = arrayOf("com.example.dsdigital.mapper"))
```

- 使用mybatis同样失败，不报错，但是不成功(线程被阻塞)
##### 解决：
- 在进入多线程代码块之前，使用cout或save等jpa方法
##### 原因：
- 尚不确定
- 推测是与jpa/hibernate懒加载机制有关
- **首先它在查询完数据库将数据映射到bean字段时做了偷梁换柱，将集合字段替换为自己组装好的集合对象，并且将hibernate操作数据库的核心Session缓存了进来。在获取该懒加载字段的值时，通过toString或者size方法调用read方式来触发数据库的执行，从而完成对字段懒加载的调用。**

#### 可能的其他解决办法
- 给表加索引
- innodb在有索引的情况下加行锁，否则加表锁
- 而可能造成线程a和b都给资源x加锁，并且双方循环等待的情况

- Spring+JPA保存数据保存不进去是因为jpa给修改操作加了默认事务，所以必须加上flush()方法提交才能真正的保存数据。
- 而且保存操作的方法必须在spring中配置好事务，否则调用flush时spring会报该方法不在事务中的异常
  