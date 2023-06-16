```java
@Valid和@Validated是Spring Validation框架提供的参数验证功能。
```

二者主要作用在于 都作为标准JSR-303规范，在检验Controller的入参是否符合规范时，使用@Validated或者@Valid在基本验证功能上没有太多区别。但是在分组、注解地方、嵌套验证等功能上两个有所不同：

@Valid:
@Valid注解用于校验，所属包为：javax.validation.Valid。

用在方法入参上无法单独提供嵌套验证功能。**能够用在成员属性（字段）**上，提示验证框架进行嵌套验证。能配合嵌套验证注解@Valid进行嵌套验证。

@Validated:
@Validated是@Valid 的一次封装，是Spring提供的校验机制使用。

用在方法入参上无法单独提供嵌套验证功能。不能用在成员属性（字段）上，也无法提示框架进行嵌套验证。能配合嵌套验证注解@Valid进行嵌套验证。




