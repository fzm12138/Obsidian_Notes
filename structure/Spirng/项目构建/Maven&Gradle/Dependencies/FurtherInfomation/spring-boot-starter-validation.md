```java
Nullable Check
@Null          check if the obj is null
@NotNull       check if the obj is notNull
@NotBlank      check if the String is null and if the length>0(get rid of sopaces before and after)
@Not Empty     check if the element is null or empty

Boolean Check
@AssertTrue     check if the obj is true
@AssertFalse    check if the obj is false

Length Check
@Size(min=,max=)     check if the obj's length in this range
@Length(min=,max=)   same

Date Check
@Past          check if Date&Calender-obj's time is before now
@Future         --
@Pattern        验证String对象是否符合正则表达式规则
```




[spring-boot-starter-validation简谈\_Keyle777的博客-CSDN博客](https://blog.csdn.net/weixin_45748004/article/details/127179006)