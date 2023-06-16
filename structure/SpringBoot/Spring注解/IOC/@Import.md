- Can only be used at *classes*
- ***@Import*** could be used when import third-part package(faster and more convience than *@Bean*)

#### Three ways to use it 
- class numbers
- **importSelector**
- ImportBeanDefinitionRegistrar

- Class numbers
```java
//class数组方式
@Import({类名.class,类名.class})
public class TestDemo{}
```
- ImportSelector
	- *The class must implement the importSelector interface*
```java
//importSelector
public class TestClass implements ImportSelector{
	@Override
	public String[] selectImports(AnnotationMetadata anno){
		return new String[0]
	}
}
```
- ***Retrun value:The Class name we want to inject to IOC***
- Params:AnootationMetadata means infomations which @Import annotates
- Function selectImports could return 0 numbers but cant return null or NPL err will occur




















