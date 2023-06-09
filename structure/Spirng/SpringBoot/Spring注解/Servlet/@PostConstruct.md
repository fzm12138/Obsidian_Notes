- @PostConstruct 与@PreDestroy 在java EE5 开始被加入用以 affect Servlet lifecycle
```java
@PostConstruct
 
public void someMethod(){}
 
或者
 
public @PostConstruct void someMethod(){}
```

- 被@PostConstruct 的方法会在server加载Servlet时执行并且智慧被服务器执行一次
- PostConstruct在构造函数之后执行,init()方法之前执行
- PreDestroy()方法在Destroy() 方法后执行
### Excute order
```java
Constructor--->@Autowired--->@PostConstruct
```

- Acutally if Obj p inject into Obj a ,then u must generate obj-a and obj-b first
- So if class A contains variable p being annotate with @Autowired then the injection of this @Autowired happens after A's constructor
- If wants to do something when the obj is inititalizing,and these initializes needs injection,then cant implent in constructor