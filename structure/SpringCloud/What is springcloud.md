Reference:[Spring Cloud](https://spring.io/projects/spring-cloud)
- 将一个服务器中的众多服务，或几台服务器中的众多服务分类解耦
- 把类似的功能交给同一个集群来做
- 把耦合的功能剥离出来，按业务、功能把它们作为微服务放在服务器上
- 这个服务器只提供一个，或较少的服务
- 将超大的服务逻辑解耦成小服务，均匀分布在各自服务器中
#### 注册中心Euraka
- 客户先访问注册中心获得服务名单
- 根据相应的负载方法各自访问
	- ***负载均衡***
#### Zuul 网关
- 负责路由
- 通过简单配置进行身份验证
	- shiro&&spring security
- 权限认证
#### Hystrix熔断器
- 服务结果、异常信息
- 防止大量请求等待，防止瘫痪
- 将某事故的蔓延熔断（服务间隔离）
***这些组件也要注册到Eureka注册中心***

#### SpringCloud是框架集合
 - 构建了
	- 服务治理(Eureka)
	- 配置中心
	- 消息总线
	- 负载均衡
	- 断路器
	- 数据监控
	- 分布式会话
	- 集群状态管理
	- ..........
- SpringCloud包含多个子项目（针对分布式系统中的多个不同开源产品）
	- Springcloud Config
	- Springcloud Netfilx
	- Springcloud CloudFoundry
	- Springcloud AWS
	- Springcloud Security
	- Springcloud Commons
	- Springcloud Zookeeper
	- Springcloud CLI
	- .............
- SpringCloud 特性，适用场景
	- 基于版本的分布式配置管理
	- 服务注册与发现
	- 路由
	- 服务间调用(依赖)
	- 负载均衡
	- 断路器
	- 全局锁
	- 选主以及集群状态管理
	- 分布式消息服务
#### SpringCloud核心是服务治理
- 通过整合Netflix的相关产品来实现
- Eureka(服务注册和发现)
- Hystrix(断路器)
- Ribbon(负载均衡)
- Rest客户端Feign
- Zuul智能服务路由
- Spectator、Servo、Atlas 监控数据收集和展示
- Archaius  配置读取
- RxJava 提供Controller层Reactive封装
- 针对Feign和Rxjava并部署Netflix的产品也整合到了Netflix中
