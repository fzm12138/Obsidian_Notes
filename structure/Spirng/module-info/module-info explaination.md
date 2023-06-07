```java
module 本模块名称{
	exports 对外暴露的包路径
	requires 需要依赖的其他模块的名称
}
```

- `module-info.java` is not a class,not a interface.It's describtion of module. 'modeule' isn't keyword
- `exports` exposed route to outside
	- Some modules u want other modules to access and some are not
	- Which modules u want other modules to access should wirte after `exports`
	- Just like *import* but not import it's export
- `requires` the modules current module needs
	- The modules current module needs write after `requires`
	- Only one module needn't to be wrote--- ***java.base***
	- 