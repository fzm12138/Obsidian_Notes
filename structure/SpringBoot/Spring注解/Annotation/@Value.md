动态读取配置文件中某个系统属性
eg:
```java
@Service
public class UserService{
	@Value("${susan.test.userName}")
	private String userName;
	public String test(){
		System.out.println(userName);
		return userName;
	}
}
```