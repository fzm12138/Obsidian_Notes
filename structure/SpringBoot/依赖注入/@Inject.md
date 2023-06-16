 @inject

### @Inject
- spring的环境下，@inject和@Autowired是相同的
- 它们依赖注入用的都AutowiredAnnotationBeanPostProcessor这个后置处理器来处理的
- 二者的区别
	- 首先是@inject是Java EE包中的，SE环境需要单独引入
	- 另一个区别是@Autowired可以设置required=false而inject没有这个属性
