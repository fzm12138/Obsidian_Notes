Maven can't resolve the Kotlin Maven Plugin jar
Using Springboot to develop a back-end project,find out that kotlin plugins cant resolve
```xml
<groupId>org.jetbrains.kotlin</groupId>  
<artifactId>kotlin-maven-plugin</artifactId>  
```

Solution:
```xml
<groupId>org.jetbrains.kotlin</groupId>  
<artifactId>kotlin-maven-plugin</artifactId>  
<version>${kotlin.version}</version>  <!--=add this-->
```


