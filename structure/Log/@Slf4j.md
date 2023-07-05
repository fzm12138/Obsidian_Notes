Simple Logging Facade for Java
### 工作原理
允许最终用户在部署时插入所需的日志框架
- 要切换日志框架，只需要替换类路径上的slf4j绑定
	- 比如将java.util.logging切换到log4j 只需要将slf4j-jdk14-1.8.0-beta2.jar替换为slf4j-log4j12-1.8.0-beta2.jar
- slf4j就是众多日志接口的集合，不负责具体日志实现，之在拜尼一世负责寻找合适的日志系统进行绑定
- 具体有哪些接口，全部定义在slf4j-api中，查看源码可见
	- 除了 LoggerFactory以外都是接口定义
- applicaiton通过slf4j桥接器桥接不同的日志框架，通过slf4j api进行日志打印
- 本质上slf4j是通过不同桥接器对接了不同日志框架，具体日志打印仍然由日志框架实现
### 工作流程
- 通过slf4j-api访问桥接器slf4j-log4j12生成LoggerFactory对象，
- 通过LoggerFactory对象的getLogger返回桥接器的LoggerAdapter对象
- 通过LoggerAdapter的info方法输出日志
#### 细节
1. SLF4J的工作流程核心包含获取Logger对象流程和打印日志流程。
2. SLFTJ通过slf4j-api调用log4j桥接器slf4j-log4j12的StaticLoggerBinder生成LoggerFactory对象。
3. SLFTJ通过slf4j-api的getLogger方法访问桥接器生产Logger对象。
4. SLFTJ通过桥接器的Logger对象实现日志的格式化和打印

```java
@Slf4j // 相当于： private static Logger log = LoggerFactory.getLogger(WeixinPayService.class);
```
