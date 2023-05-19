- Function level annotation
- Mostly using in the class which is being anootated by @configuration(and the class with @Component)
example:
```java
@Configuration
public class AppConfig {
 
    @Bean
    public TransferService transferService() {
        return new TransferServiceImpl();
    }
 
}
```





