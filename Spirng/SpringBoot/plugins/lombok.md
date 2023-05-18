### 引入：
pom.xml里引入lombok依赖
```xml
<dependency>
	<artifactId>lombok</artifactId>
	<groupId>org.projectlombok</groupId>
	<version>1.18.22</version><!--注意统一版本-->
</dependency>
```
#### 常用注解
```js
@Slf4j
//生成所有的get
@Getter
//生成所有的set
@Setter
@EqualsAndHashCode(of={"name","id"})//可以指定哪些字段参与
@ToString(of={"name","id"})//指定字段
//无参构造，加上private就有了单例
@NoArgsConstructor(access=Accesslevel.PRIVATE)
//全参构造
@AllArgsConstructor

@Data//使用后getter setter tostring equals合一
@Value

@Accessors

@Builder

@Singular
```

