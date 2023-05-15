kotlin can't load dependencies: 
spring alter maven lack of dependencies
solution: 
enforce maven install all dependencies
	open maven bar and click 'Excute maven goal'
```python
# mvn clean install -e -U
```
And after that maybe maven still can't resolve the Kotlin Maven Plugin jar
- Add this in your pom
```xml
<groupId>org.jetbrains.kotlin</groupId>  
<artifactId>kotlin-maven-plugin</artifactId>  
<version>${kotlin.version}</version>  <!--=add this-->
```

