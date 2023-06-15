### What is it ?
- recording to different languages to response differently
Such as :
1. There's a info-table for users to fill infomations and lies a inputbox for name 
2. The browser support languages-switching
- If u choose Chinese
```c
姓名：一个输入框
```
- If u choose English
```go
Full name：一个输入框
```
This is what it's used for

**So apparently if the app wants to support international it should now what language it is** 
- in java using `java.util.Locale` to represent region-obj
```java
public Locale(String language,String country){
	this(language,country,"");
}
```

```
2个参数：

language：语言

country：国家

语言和国家这两个参数的值不是乱写的，国际上有统一的标准：

比如language的值：zh表示中文，en表示英语，而中文可能很多地区在用，比如大陆地区可以用：CN，新加坡用：SG；英语也是有很多国家用的，GB表示英国，CA表示加拿大

国家语言简写格式：language-country，如：zh-CN（中文【中国】），zh-SG（中文【新加坡】），en-GB（英语【英国】），

en-CA（英语【加拿大】）。

还有很多，这里就不细说了，国家语言编码给大家提供一个表格：http://www.itsoku.com/article/282
```

Class Locale had already construct lots of objs could use directly
```java
static public final Locale SIMPLIFIED_CHINESE = createConstant("zh", "CN"); //zh_CN
static public final Locale UK = createConstant("en", "GB"); //en_GB
static public final Locale US = createConstant("en", "US"); //en_US
static public final Locale CANADA = createConstant("en", "CA"); //en_CA
```

#### How to active it?
- Interface `MessageSource`
- Spring's internationalization is supported by this interface
`org.springframework.context.MessageSource`
- It has three inner common functions to get internationalization informations:
```java
public interface MessageSource {
 
    /**
     * 获取国际化信息
     * @param code 表示国际化资源中的属性名；
     * @param args用于传递格式化串占位符所用的运行参数；
     * @param defaultMessage 当在资源找不到对应属性名时，返回defaultMessage参数所指定的默认信息；
     * @param locale 表示本地化对象
     */
    @Nullable
    String getMessage(String code, @Nullable Object[] args, @Nullable String defaultMessage, Locale locale);
 
    /**
     * 与上面的方法类似，只不过在找不到资源中对应的属性名时，直接抛出NoSuchMessageException异常
     */
    String getMessage(String code, @Nullable Object[] args, Locale locale) throws NoSuchMessageException;
 
    /**
     * @param MessageSourceResolvable 将属性名、参数数组以及默认信息封装起来，它的功能和第一个方法相同
     */
    String getMessage(MessageSourceResolvable resolvable, Locale locale) throws NoSuchMessageException;
 
}
```

Three common implements classes
- ResourceBundleMessageSource
	- 这个是基于Java的ResourceBundle基础类实现，允许仅通过资源名加载国际化资源
- ReloadableResourceBundleMessageSource
	- 这个功能和第一个类的功能类似，多了定时刷新功能，允许在不重启系统的情况下，更新资源的信息
- StaticMessageSource
	- 它允许通过编程的方式提供国际化信息，一会我们可以通过这个来实现db中存储国际化信息的功能
#### Three steps using internationalization in spring
Usually when we use spring will using the containers with `ApplicaionContext`, these containers usually are the interfaces extended `AbstractApplicationContext`
- Step one: Construct internationaliztion files
	- Step two: 向container 中注册一个MessageSourcce type 的bean bean's name has to be : messageSource
- Step three: 调用AbstractApplicationContextr中的getMessage来获取国际化信息，内部交给第二部中注册的messageSource名称的bean 进行处理

### Example:
- construct internationalization file
- name_language_region.properties
Let's construct three files and put them into this log
```c
com/javacode2018/lesson002/demo19/
```

message.propertites
```c
name=您的姓名
personal_introduction=默认个人介绍:{0},{1}
#这个文件名称没有指定Local信息，当系统找不到的时候会使用这个默认的
```

message_zh_CN.properties：中文【中国】
```c
name=姓名
personal_introduction=个人介绍:{0},{1},{0}
```

message_en_GB.properties：英文【英国】
```c
name=Full name
personal_introduction=personal_introduction:{0},{1},{0}
```

spring 中注册国际化的bean
- notice: the type must be `MessageSource` bean's name must be `messageSource` we use ResourceBundleMessageSource 
```java
package com.javacode2018.lesson002.test19.demo1;
 
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.support.ResourceBundleMessageSource;
 
@Configuration
public class MainConfig1 {
    @Bean
    public ResourceBundleMessageSource messageSource() {
        ResourceBundleMessageSource result = new ResourceBundleMessageSource();
        //可以指定国际化化配置文件的位置，格式：路径/文件名称,注意不包含【语言_国家.properties】含这部分
        result.setBasenames("com/javacode2018/lesson002/demo19/message"); //@1
        return result;
    }
}
//@1：这个地方的写法需要注意，可以指定国际化化配置文件的位置，格式：路径/文件名称,注意不包含**【语言_国家.properties】**含这部分
```

Test
```java
package com.javacode2018.lesson002.test19;
 
import com.javacode2018.lesson002.test19.demo1.MainConfig1;
import org.junit.Test;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
 
import java.util.Locale;
 
public class MessageSourceTest {
 
    @Test
    public void test1() {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(MainConfig1.class);
        context.refresh();
        //未指定Locale，此时系统会取默认的locale对象，本地默认的值中文【中国】，即：zh_CN
        System.out.println(context.getMessage("name", null, null));
        System.out.println(context.getMessage("name", null, Locale.CHINA)); //CHINA对应：zh_CN
        System.out.println(context.getMessage("name", null, Locale.UK)); //UK对应en_GB
    }
}
```

### We could save the informations of internationalization in DB
The class `StaticMessageSource` has two important functions
```java
public void addMessage(String code, Locale locale, String msg);
public void addMessages(Map<String, String> messages, Locale locale);
```
Using them two to add internationalization infos
eg:
```java
package com.javacode2018.lesson002.test19.demo3;
 
import org.springframework.beans.factory.InitializingBean;
import org.springframework.context.support.StaticMessageSource;
 
import java.util.Locale;
 
public class MessageSourceFromDb extends StaticMessageSource implements InitializingBean {
    @Override
    public void afterPropertiesSet() throws Exception {
        //此处我们在当前bean初始化之后，模拟从db中获取国际化信息，然后调用addMessage来配置国际化信息
        this.addMessage("desc", Locale.CHINA, "我是从db来的信息");
        this.addMessage("desc", Locale.UK, "MessageSource From Db");
    }
}
```

sping config-class
```java
package com.javacode2018.lesson002.test19.demo3;
 
import org.springframework.context.MessageSource;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
 
@Configuration
public class MainConfig3 {
    @Bean
    public MessageSource messageSource(){
        return new MessageSourceFromDb();
    }
}
```


##### Why bean's name must be messageSource
When start a container will call function `refresh`
```c
org.springframework.context.support.AbstractApplicationContext#refresh 
内部会调用
org.springframework.context.support.AbstractApplicationContext#initMessageSource
这个方法用来初始化MessageSource,方法内部会查找当前容器中是否有messageSource名称的bean，如果有就将其作为处理国际化的对象
如果没有找到，此时会注册一个名称为messageSource的MessageSource
```
#### 自定义bean中使用国际化
- it's easy to use a internationalization with self-defined bean, just implements this interface and spring will call this function automatically and injection `MessageSource` then we can use MessageSource to get internationalizaiton infos
```java
public interface MessageSourceAware extends Aware {
    void setMessageSource(MessageSource messageSource);
}
```

