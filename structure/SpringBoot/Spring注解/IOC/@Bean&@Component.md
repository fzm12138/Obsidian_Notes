### ***@Bean***
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

### ***@Component***
- Class level annotation


******

#### ***Both of them logging a 'bean' into IOC***

@Bean could use a third-party method and @Component cant manage that 