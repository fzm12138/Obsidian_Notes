- Scheduler调用一个job就会将JobExecutionContext传递给Job的execution()方法
- 但是查看源码看起来是:execute方法
```java
public interface Job {
    void execute(JobExecutionContext var1) throws JobExecutionException;
}
```


