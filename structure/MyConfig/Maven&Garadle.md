## 首先注意：
- 有时候用maven方式会报错，先检查你的结构(比如dependency是否在dependecies下)
- 为你添加的依赖添加`<version>#{你的版本号}</version>
##### spring-boot-starter-validation
```js
dependencies{
	implementation 'org.springframework.boot:spring-boot-starter-validation'
}
```
###### Maven方式
```xml
<dependency>  
	<groupId>org.springframework.boot</groupId>  
	<artifactId>spring-boot-starter-validation</artifactId>  
</dependency>
```
进行各种验证
###### eg:
- Nullable Check
	- @Null          check if the obj is null
	- @NotNull       check if the obj is notNull
	- ..........
#####  spring-boot-starter-web'
```js
dependencies{
	implementation 'org.springframework.boot:spring-boot-starter-web'
}
```
###### Maven方式
```xml
<dependency>  
	<groupId>org.springframework.boot</groupId>  
	<artifactId>spring-boot-starter-websocket</artifactId>  
	<version>2.6.13</version>  
</dependency>
```

- Web启动器，使项目成为一个web项目
- 提供Serlet容器以及SpringMVC依赖
- 主流，但是现在有新的东西，我没用明白(webflux, 需要用r2dbc替换mysql-connector)

##### JPA
```js
dependencies{
	implementation 'org.springframework.boot:spring-boot-stater-data-jpa'
}

```
###### Maven方式
```xml
<!--JPA-->
<dependency>
	<groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
```
- JPA ORM框架 提供数据库和实体类映射
- 信息很多，单独学

##### MQ
```js

```
###### Maven方式
```xml
<dependency>  
	<groupId>org.springframework.boot</groupId>  
	<artifactId>spring-boot-starter-amqp</artifactId>  
	<version>2.6.13</version>  
</dependency>
```






