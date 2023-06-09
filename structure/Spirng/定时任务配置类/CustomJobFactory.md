```kotlin

/** 指定将Job由Spring容器管理  */
@Component
class CustomJobFactory : SpringBeanJobFactory(), ApplicationContextAware {
    @Transient
    private var capableBeanFactory: AutowireCapableBeanFactory? = null
    override fun setApplicationContext(@NotNull applicationContext: ApplicationContext) {
        capableBeanFactory = applicationContext.autowireCapableBeanFactory
    }

    @NotNull
    @Throws(Exception::class)
    override fun createJobInstance(bundle: TriggerFiredBundle): Any {
        val jobInstance = super.createJobInstance(bundle)
        capableBeanFactory!!.autowireBean(jobInstance)
        return jobInstance
    }
}
```