### 用处
**若看到某个类非常多的信息，要用mybatis查询指定字段，就许需要@JsonInclude()注解了。**
- 在类上加入@JsonInclude(JsonInclude.Include.NON_NULL)
- 表明此类为null的字段不参加序列化
- 如果在类上面，则对此类全部属性起作用
eg:
```java
@JsonInclude(JsonInclude.Include.NON_NULL)
public Class Student{

	private String id;
	
	private String name;
}
```

eg:
```java
public Class Student{

	@JsonInclude(JsonInclude.Include.NON_NULL)
	private String id;

	private String name;
}
```

```js
include.Include.ALWAYS -------------->默认
Include.NON_DEFAULT ------------->属性为默认值不序列化
Include.NON_EMPTY ---------------->属性为 空（“”） 或者为 NULL 都不序列化
Include.NON_NULL ------------------>属性为NULL 不序列化

```