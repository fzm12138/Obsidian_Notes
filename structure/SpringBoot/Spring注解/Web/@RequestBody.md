- 结合POST
- 可以和`@RequetParam`结合
- ***只能有一个***
```c
RequestBody 接收的是请求体里面的数据；而RequestParam接收的是key-value 里面的参数，所以它会被切面进行处理从而可以用普通元素、数组、集合、对象等接收
```
- 若参数在请求体中，要用`@RequstBody`才能收到
- 若不在请求体中用`@RequestParam`
### 前后端传信息时
- 若后端参数是一个对象，前端传递json时必须满足：
	- @RequestBody注解的类将在HTTP的输入流（含请求体）装配到目标类，
		- 根据json中的key匹配对应实体类的属性，符合则使用setter()进行赋值
	- json串中，若value为`""` ，后端是string则获得`""` ,否则为null
		- 可以做判空校验
	- json串中若value是`null`，则后端收到`null`
	- 若某个参数没有值，在传给后端时，要么不写入json，要么写`null`或`""`
### @RequsetBody与前端传入的json字符串的匹配规则
1. 根据不同的Content-Type等情况,Spring-MVC会采取不同的HttpMessageConverter实现来进行信息转换解析
2. 最常用的：前端以Content-Type 为application/json,传递json字符串数据;后端以@RequestBody
##### 解析json数据大体流程：
-  Http传递请求体信息，最终会被封装进`com.fasterxml.jackson.core.json.UTF8StreamJsonParser`中
- Spring采用`CharacterEncodingFilter`设置了默认编码为UTF-8
- `public class BeanDeserializer extends BeanDeserializerBase implements java.io.Serializable`中，通过 `public Object deserializeFromObject(JsonParser p, DeserializationContext ctxt) throws IOException`方法进行解析

### 在对象的属性上使用的注解
1. @JsonAlias注解，实现:json转模型时，使json中的特定key能转化为特定的模型属性;但是模型转json时，对应的转换后的key仍然与属性名一致
```kotlin
@JsonAlias(value={"name","name123"})
var name:String
```
- 此时从json转换过来时，name或者name123都能识别
2. 若`@JsonAlias`注解中value只指定了一个值，那么只能对这个值进行识别
3. `@JsonAlias` 注解需要依赖于setter、getter，而`@JsonProperty`注解不需要
4. 默认key与属性匹配，大小写敏感
5. 多个相同的key则会因为setter被最后一个key覆盖
6. 