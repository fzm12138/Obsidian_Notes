@Resousce

### @Resource
- JSR-250定义的注解
- Spring在CommonAnnotationBeanPostProcessor实现了对JSR-250的注解的处理

#### @Resource有两个属性，name和type
- spring中name属性定义为bean的名字
- type是bean 的类型
#### 如果属性加上@Resource注入流程则是:
- 如果同时指定了name和type，则spring上下文中找到唯一匹配的bean进行装配，找不到抛出异常
- 指定了name，从上下文中查找名称匹配的bena装配，找不到则抛出异常
- 如果指定了type，则从上下文找到类型匹配的唯一bean进行装配，找不到或者找到多个都抛出异常
- 都每指定按照byName方式进行装配，没匹配按byType进行装配


因此可以使用@Resource代替@Autowired，也可以使@RequiredArgsConstructor构造器方式注入，这种形式是Spring推荐方式
此包是lombok下的注解
```java
@RequiredArgsConstructor
public class UserDaoImpl {
	private final User user;
```



