- Can only be used at *classes*
- ***@Import*** could be used when import third-part package(faster and more convience than *@Bean*)

#### Three ways to use it 
- class numbers
- importSelector
- ImportBeanDefinitionRegistrar

```java
//class数组方式
@Import({类名.class,类名.class})
public class TestDemo{}
```

