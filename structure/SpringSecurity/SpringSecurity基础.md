## 环境准备
- springweb
- lombok、mybatis、log4j
- 集成一个前端模板(jsp、thymeleaf、freemarker等)

## SpringSecurity引入
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

## HttpBasic 模式的应用场景
- 最简陋的方式
- ***不安全***
### HttpBasic登录认证模式
```java
@Configuration
public class SecurityConfig extends WebSecurityConfigurerAdapter {
   
   @Override
   protected void configure(HttpSecurity http) throws Exception {
      http.httpBasic()//开启httpbasic认证
      .and()
      .authorizeRequests()
      .anyRequest()
      .authenticated();//所有请求都需要登录认证才能访问
   }

}
```
启动项目，在项目后台有这样的一串日志打印，冒号后面的就是默认密码。
```c
Using generated security password: 0cc59a43-c2e7-4c21-a38c-0df8d1a6d624
```
可以通过application.yml方式配置用户名密码
```yml
spring:
    security:
      user:
        name: admin
        password: admin
```

![[HttpBasic原理.png|1125]]

![[过滤器链.png|1575]]

