Request.js有三个显眼的方法：
- request拦截器
- response拦截器
- 通用下载方法
```js
//request拦截器 Get
//request拦截器对请求进行了封装，发送Get请求，携带参数时候应该用param
if(config.method=='get'&&config.params){
	let url=config.url+'?' +tansParams(config.params);
	url=url.slice(0,-1);
	config.params={};
	config.url=url;
}
//可以将get请求自动变为:htttp://xxx:prot/xx?key1=v1&key2=v2这样的格式
```

```
//Get拦截器 post


```