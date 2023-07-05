### What is it?
- 提供精确的系统记录
- 描述离散时间
- 通过日志系统收集，存储到存储引擎中方便查询
#### 作用
- 打印调试：
	- 记录变量、某一段逻辑（记录程序运行了哪些代码）
- 问题定位：
	- 线上无法debug，测试环境又费时费力
	- 可以记录流量，后期可以使用ELK
- 用户行为日志
	- 记录用户的操作行为---- 监控、推荐等等
- 根因分析：
	- 在关键地方记录日志，方便在终端定位问题
### 日志的级别
***TRACE<DEBUG<INFO<WARN<ERROR<FATAL 优先级别***
SpringBoot默认级别是INFO，比INFO级别小的不显示
#### root级别(yml文件中)
```yml
  logging:
        level:
              root: warn #root:代表的是项目所有日志
```
若将root日志界别设为warn，则项目的所有INFO日志将不再显示，只显示warn及以上的级别
#### package级别
代表指定包下的日志对应的日志级别，不是这个包下的采用默认的INFO级别
如何设置自己的日志格式？
```yml
日志格式有哪些？？
 # %d{yyyy/MM/dd-HH:mm:ss:SSS}日志输出时间
 # [%thread]：输出日志的线程名字
 # %-5level ：日志级别 并且使用5个字符靠左对齐
 # %logger-：日志输出者的名字
 # %msg ：日志消息  %n换行
```

```yml
    1.logging.file.path：
        指定日志文件的路径，不指定名称，默认的名称是spring.log
        logging:
           file:
            path: C:\demo\hello3  #日志文件路径
     2.logging.file.name：
        可以指定指定日志文件的路径和日志文件的称
        logging:
          file:
            name: C:\demo\hello3\hello.log  #日志文件名带路径
    在此盘的路径中就会存储日志文件信息
```
#### application.yml中怎么写
```yml
logging:
  level:
    com.tjetc.mapper: info
  #file:
     #name:
        #C:/Users/ASUS/Desktop/log/hello.log
  #实现根据日期生成日志
  config:
    #引入配置
    classpath:logback-spring.xml
    #填写日志输出的路径，不写则引用项目相对路径
    #path: D:\\tmp\\log

```
