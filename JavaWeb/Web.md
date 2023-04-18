*@Author fzm*
1.1分类
**静态web：**
- html css
- 给所有人看到数据不会发生变化
**动态web：**
- 每个人在不同时间/地点看到的信息不同
- 几乎所有网站（淘宝、京东.....）
- 常用的技术栈：
	- Servket 、JSP、ASP、PHP
- 在java中动态web资源开发的技术栈统称JavaWeb
-----
1.2 web applicaiton
- 提供浏览器访问的application
- 这个统一的web资源放在同一个文件夹下，web应用程序-->Tomcat：服务器
- one web application made  up by several parts:
	- html、css、js
	- java程序
	- jar包
	- 配置文件
Web application编写完成后若想提供给外界访问，需要一个服务器统一管理
------
**谈谈网站是如何进行访问的？
- **输入域名**
- **检查本机配置文件下有没有这个域名映射**
	- **有，直接返回对应ip**
	- **无，访问DNS服务器找映射（全世界的域名都在此管理）**
		- **找到返回，找不到返回找不到**
-----
1.3 网站的结构
```java
-web apps //Tomcat服务器的web目录
	-ROOT
	-xxxxxxx //网站的目录名
		-WEB-INF
			-classes //java程序
			-lib //web应用依赖的jar包
			-web.xml //默认的网站配置
		index.html//默认的首页
		-static
			-css
				-styles.css
			-js
			-img
```


