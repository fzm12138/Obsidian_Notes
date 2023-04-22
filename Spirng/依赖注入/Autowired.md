### Spring 由三种依赖注入方式
- 基于属性(filed)注入
	- 在bean的变量上进行依赖注入
	- 本质上是通过反射的方式直接注入到 field
```Java
@Autowired
UserService userService;
```

- 基于set方法注入
	- 通过对应变量的setXXX()方法上使用注解
```java
private UserService userService;
 
@Autowired
public void setUserService(UserService userService) {
    this.userService = userService;
}
//说明：在 Spring 4.5 及更高的版本中，setXXX 上面的 @Autowired 注解是可以不写的。
```

- 基于构造器注入
	- 将各个必须的依赖全部放在带有注解构造方法的参数中
	- 并在构造方法中完成对应变量的初始化
```java
private final UserService userService;
 
@Autowired
public UserController(UserService userService) {
    this.userService = userService;
}
```

#### 属性注入简洁但是有问题
##### NO.1
```java
@Autowired
private UserService userService;
 
private String company;
 
public UserServiceImpl() {
    this.company = userService.getCompany();
}
```
- 编译的时候不报错，运行空指针
Java初始化一个类时，按照 静态变量/静态语句块->实例变量/初始化语句块->构造方法->@Autowired顺序
- 故执行这个类的构造方法时，user对象尚未注入

##### NO.2
- 不能有效地指名依赖
- 常见bug：
	- 依赖注入的对象为null
	- 启动依赖容器时遇到这个问题是配置的依赖少了注解
	- 这种方式过于依赖注入容器
	- 没有启动整个依赖容器时，此类不能运转，反射时无法提供这个类需要的依赖
##### NO.3
- 依赖注入的核心是容器管理的类不应该依赖被容器管理的依赖
- 如果此类使用了依赖注入的类，那么这个类摆脱这几个依赖也能正常运行
- 变量注入保证不了上述特点
#### Solution:
一般开发需要注入属性时都需要三个注解
```java
@Autowired 
@Inject
@Resource
```

```java
public interface IndexService {
 
    void sayHello();
}
 
@Service
public class IndexServiceImpl implements IndexService {
 
    @Override
    public void sayHello() {
        System.out.println("hello, this is IndexServiceImpl");
    }
}
 
@Service
public class IndexServiceImpl2 implements IndexService {
 
    @Override
    public void sayHello() {
        System.out.println("hello, this is IndexServiceImpl2");
    }
}
复制代码
```
##### @Autowired
为spring框架提供注解
匹配bean的过程

- 按照type在上下文查找匹配的bean
- 若有多个bean，按照name进行匹配
	- 如果有@Aualifier注解，按照@Aualifier指定的name进行匹配，查找name为IndexServiceImpl2的bean
	- 如果没有，按照变量名进行匹配，查找name为IndexService的bean
- 若匹配不到，则报错
```java
@Autowired(required=false) 则注入失败不抛出异常
```

 
[[@Inject]]
[[@Resource]]



















