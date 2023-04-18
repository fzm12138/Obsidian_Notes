*@Author fzm*
**1.1什么是http**
- 文本：html、string.....
- 超文本:pics、music、video.....
- **http默认80端口 https默认443**
- https是‘安全的’
-----
**1.2  http1.0  http1.1**
- HTTP/1.0
	- user可以与web server连接，只能获得一个资源（只能请求到一次资源）
- HTTP/1.1
	- 可以获得多个web资源
-------
1.3 HTTP请求
- user--请求-->服务器
eg:
```html
1.  Request URL:https://www.baidu.com/  <---请求的url--->
2.  Request Method:
    GET                 <---get/post方法--->
3.  Status Code:
    200 OK             <---状态码-->
4.  Remote Address:
    127.0.0.1:10809       <---请求的地址和端口--->
5.  Referrer Policy:
    unsafe-url
```
1、请求行
- 请求行中的请求方式:
	- GET/POST etc...
		- GET更高效
			- 参数暴露在URL上，不能传递敏感信息
			- 一次请求能携带的参数更少，大小有限制
		- POST更安全
			- 参数不暴露
			- 参数无限制
2、消息头
```java
Accept: //告诉浏览器它所支持的类型
Accept-Encoding://支持哪种编码格式
Accept-Language://告诉浏览器它的语言环境
Cache-Control://缓存控制
Connection://告诉浏览器请求完成是断开还说保持连接
```
1.4HTTP响应
- server---响应--->user
```html
1.  Content-Length:
    53
2.  Content-Type:
    text/plain; charset=UTF-8
3.  Date:
    Sun, 16 Apr 2023 07:58:45 GMT
```

1.4.1响应体
```java
Accept: //告诉浏览器它所支持的类型
Accept-Encoding://支持哪种编码格式
Accept-Language://告诉浏览器它的语言环境
Cache-Control://缓存控制
Connection://告诉浏览器请求完成是断开还说保持连接
Refresh://告诉user多久刷新
Location://让网页重定位
```

















