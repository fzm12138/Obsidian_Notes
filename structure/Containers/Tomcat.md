## Tomcat是Web服务器和Servlet的结合体

***JSP/Servlet容器的基本功能是把动态资源转换成静态资源***
- jsp是动态资源
	- 可拼装
	- 随时间变化
- HTML是静态资源
### 什么是Web服务器
- 将某主机上的资源映射为一个URL供外界访问
### Servlet
- Servlet容器，存放着Servlet对象
- 我们能通过Web服务器映射的URL访问资源，需要三个过程
	- 接收请求
	- 处理请求
	- 响应请求
- Any applicaitons needs all three steps
	- The request recive and response request are common function,has no diffrences
		- So `Reciving` and `Response` constructed to ***Web Server***
	- But `Processing` is different,so it's made into ***Servlet***
- Then as internet developing, Three-tier architecture shows
	- So some logic get out of `Servlet` and distribute to `Service` and `Dao`
	- But Servlet is not good at output HTML page to browser,so ***JSP*** shows

#### SpringMVC's core component DispatcherServlet is a Servlet
- it packaged on the basic of HttpServlet

# Three components of JavaWeb
- ***Injection*** and ***Callback***
