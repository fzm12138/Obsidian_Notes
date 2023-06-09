```kotlin
import lombok.extern.slf4j.Slf4j
import org.hibernate.query.sqm.tree.SqmNode.log
import org.quartz.Scheduler
import org.quartz.SchedulerException
import org.quartz.SchedulerFactory
import org.quartz.impl.StdSchedulerFactory
import org.springframework.beans.factory.annotation.Autowired
import org.springframework.context.ApplicationListener
import org.springframework.context.annotation.Bean
import org.springframework.context.event.ContextRefreshedEvent
import org.springframework.stereotype.Component

/**
 * 此方法是为了启动服务的时候，自动运行定时任务start()，
 * 还可以利用@PostConstruct启动，还有CommandLineRunner 接口实现也可以
 * **/
@Slf4j
@Component
class ApplicationStartQuartzJobListener : ApplicationListener<ContextRefreshedEvent> {
    @Autowired
    lateinit var quartzManager: QuartzManager
    override fun onApplicationEvent(event: ContextRefreshedEvent) {
        try {
            quartzManager.startJobs()
            println("jobs started...")
        } catch (e: Exception) {
            log.warn("Caught exception with schedule jobs".plus(e))
        }
    }

    /**
     * 初始注入scheduler
     * @return
     * @throws SchedulerException
     **/
    @Bean
    @Throws(SchedulerException::class)
    fun scheduler(): Scheduler? {
        val schedulerFactoryBean: SchedulerFactory = StdSchedulerFactory()
        return schedulerFactoryBean.scheduler
    }
}
```