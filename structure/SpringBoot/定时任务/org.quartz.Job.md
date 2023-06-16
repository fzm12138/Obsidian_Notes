- Job是一个工作任务
- 当Scheduler决定运行Job时，execute()方法会执行
- 具体可以做什么：
	- 定时执行任务
- **也就是任何java能做的任务都可以称为一个job**
---
- org.quartz.Job接口是一个无状态的任务接口
- 实现此接口的任务每当触发器触发时都会准时执行
- 调度器并不关心此任务是否有其他实例正在运行
- **若任务存在阻塞，可能导致大量任务实例并行执行**
- 若业务中存在不允许并行执行的任务，此时就有
```java
// org.quartz.StatefulJob接口
```
- 此接口的任务实现类不能并行执行
### Job和StatefulJob代码上的区别
- 没区别，名字不一样
- 框架只是通过接口名字来表示是无状态任务还是有状态任务
# OTHERS
- JobDetail
- [[JobDataMap]]
- [关于spring中的Job](https://blog.csdn.net/loveer0/article/details/83004422)