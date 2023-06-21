![[SpringCloudHelloWorldStructure.png]]
### 三种角色
- **Euraka Server** ：服务注册中心
	- 负责服务列表的注册、维护、查询等功能
- **Service Provider** : 服务提供方，同时也是一个**Eureka Client**
	- 负责将所提供的服务向***Euraka Server***进行注册、续约、注销等操作
	- 注册时提供的主要数据包括
		- 服务名、机器ip、端口号、域名等
		- 以便`服务消费方`找得到
- Service Consumer : `服务消费方` 同时也是一个**Eureka Client**
	- 向Eureka Server注册本身提供的服务
	- 示例图片中更多的是从EurekaServer获取服务列表以便发起调用
```c
服务提供方和服务消费方并不是一个严格的概念
通常消费方也是提供方
微服务构建需要遵守业务层级划分
避免循环依赖
```

