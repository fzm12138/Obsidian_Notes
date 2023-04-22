ToStringStyle.MULTI_LINE_STYLE

1.ToStringStyle.MULTI_LINE_STYLE每项属性按行输出；

2.@PreAuthorize注解会在方法执行前进行权限验证，支持Spring EL表达式，它是基于方法注解的权限解决方案。只有当@EnableGlobalMethodSecurity(prePostEnabled=true)的时候，@PreAuthorize才可以使用，@EnableGlobalMethodSecurity注解在SPRING安全中心进行设置，如下：

/**  
​  
SPRING安全中心  
```java
@author ROCKY  

@EnableGlobalMethodSecurity(prePostEnabled = true, securedEnabled = true)  
public class SecurityConfig extends WebSecurityConfigurerAdapter {  
}

//设置请求分页数据  
startPage();

拦截器？？？