实现方式很多
such as:AOP方式
- 通过方法名判断
	- 方法名中有get、select、query开头的连接slave
	- 其他连接master
- AOP实现比较繁琐，有框架：
- Apache shardingSphere
	- 开源
	- 分布式数据库中间件
	- 由JDBC、Proxy两部分构成
- ShardingSphere-JDBC定位为轻量级java框架
	- 在java的jdbc层提供额外服务
		- 使用客户端智直连数据库，以jar包形式提供服务，无需额外部署和依赖
		- 增强版JDBC驱动，完全兼容JDBC和各种ORM框架
### Example
SpringBoot+Mybatis+Mybatis-plus+druid+ShardingSphere-JDBC

```c
SpringBoot：2.0.1.RELEASE
druid：1.1.22
mybatis-spring-boot-starter:1.3.2
mybatis-plus-boot-starter：3.0.7
sharding-jdbc-spring-boot-starter:4.1.1
```

```xml
<dependency>
    <groupId>org.apache.shardingsphere</groupId>
    <artifactId>sharding-jdbc-spring-boot-starter</artifactId>
    <version>4.1.1</version>
</dependency>
```

```yaml
# 这是使用druid连接池的配置，其他的连接池配置可能有所不同
spring:
  shardingsphere:
    datasource:
      names: master,slave0,slave1
      master:
        type: com.alibaba.druid.pool.DruidDataSource
        driver-class-name: com.mysql.jdbc.Driver
        url: jdbc:mysql://192.168.0.108:3306/test_db?useUnicode=true&characterEncoding=utf8&tinyInt1isBit=false&useSSL=false&serverTimezone=GMT
        username: yehongzhi
        password: YHZ@1234
      slave0:
        type: com.alibaba.druid.pool.DruidDataSource
        driver-class-name: com.mysql.jdbc.Driver
        url: jdbc:mysql://192.168.0.109:3306/test_db?useUnicode=true&characterEncoding=utf8&tinyInt1isBit=false&useSSL=false&serverTimezone=GMT
        username: yehongzhi
        password: YHZ@1234
      slave1:
        type: com.alibaba.druid.pool.DruidDataSource
        driver-class-name: com.mysql.jdbc.Driver
        url: jdbc:mysql://192.168.0.110:3306/test_db?useUnicode=true&characterEncoding=utf8&tinyInt1isBit=false&useSSL=false&serverTimezone=GMT
        username: yehongzhi
        password: YHZ@1234
    props:
      sql.show: true
    masterslave:
      load-balance-algorithm-type: round_robin
    sharding:
      master-slave-rules:
        master:
          master-data-source-name: master
          slave-data-source-names: slave0,slave1
```

```c
sharding.master-slave-rules是标明主库和从库，一定不要写错，否则写入数据到从库，就会导致无法同步。

load-balance-algorithm-type是路由策略，round_robin表示轮询策略。

```


## The problems:
- 从机通过binlog日志从master获取数据，若延迟，就延迟，
- 关于事务：
	- 同一个线程且同一数据库连接内，若写入，以后的读都从主库读，用于保证数据一致性