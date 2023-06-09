```kotlin

import jakarta.annotation.Resource
import lombok.extern.slf4j.Slf4j
import org.apache.commons.lang3.StringUtils
import org.hibernate.query.sqm.tree.SqmNode.log
import org.jetbrains.annotations.NotNull
import org.quartz.*
import org.quartz.impl.StdSchedulerFactory
import org.springframework.beans.BeansException
import org.springframework.context.ApplicationContext
import org.springframework.context.ApplicationContextAware
import org.springframework.stereotype.Component

/**
 * @author fzm
 * @since 2023-06-09
 * **/

/** Reference: https://blog.csdn.net/limingcai168/article/details/85008721  */
@Slf4j
@Component
class QuartzManager : ApplicationContextAware {
    @Resource
    private val customJobFactory: CustomJobFactory? = null
    private var applicationContext: ApplicationContext? = null
    private var scheduler: Scheduler? = null

    @Throws(BeansException::class)
    override fun setApplicationContext(@NotNull applicationContext: ApplicationContext) {
        this.applicationContext = applicationContext
    }

    @Throws(SchedulerException::class)
    fun startJobs() {
        scheduler = schedulerFactory.scheduler
        scheduler!!.setJobFactory(customJobFactory)
        //找到所有AbstractTask类的子类，获取所有子任务
        val tasks = applicationContext!!.getBeansOfType(AbstractTask::class.java)
        tasks.forEach { (k: String, v: AbstractTask) ->
            println("Job's name is $k , job js $v")
            //获取所有的任务的cron表达式并添加到任务中
            val cronExpression: String? = v.cronExpression

            if (StringUtils.isNotBlank(cronExpression)) {
                addAndExecuteJob(k, v.javaClass.name, cronExpression!!)
            }
        }
    }

    /** 增加并执行定时任务  */
    private fun addAndExecuteJob(jobName: String, jobClass: String, cronExp: String) {
        println("JobName is $jobName")
        println("JobClass is $jobClass")
        if (!CronExpression.isValidExpression(cronExp)) {
            log.warn("Illegal cron expression format({})".plus(cronExp))
            return
        }
        try {
            val jobKey = JobKey(jobName, JOB_DEFAULT_GROUP_NAME)
            val jobDetail =
                JobBuilder.newJob().withIdentity(jobKey).ofType(Class.forName(jobClass) as Class<Job?>).build()
            val trigger: Trigger =
                TriggerBuilder.newTrigger()
                    .forJob(jobDetail)
                    .withSchedule(CronScheduleBuilder.cronSchedule(cronExp))
                    .withIdentity(TriggerKey(jobName, TRIGGER_DEFAULT_GROUP_NAME))
                    .build()

            if (scheduler!!.checkExists(jobKey)) {
                deleteJob(jobName)
            }
            scheduler!!.scheduleJob(jobDetail, trigger)
            scheduler!!.start()
        } catch (e: Exception) {
            log.warn("QuartzManager add job failed".plus(e))
        }
    }

    /** 更新定时任务  */
    fun updateJob(jobName: String?, cronExp: String?) {
        if (!CronExpression.isValidExpression(cronExp)) {
            log.warn("Illegal cron expression format({})".plus(cronExp))
            return
        }
        val jobKey = JobKey(jobName, JOB_DEFAULT_GROUP_NAME)
        val triggerKey = TriggerKey(jobName, TRIGGER_DEFAULT_GROUP_NAME)
        try {
            if (scheduler!!.checkExists(jobKey) && scheduler!!.checkExists(triggerKey)) {
                val jobDetail = scheduler!!.getJobDetail(jobKey)
                val newTrigger: Trigger = TriggerBuilder.newTrigger().forJob(jobDetail)
                    .withSchedule(CronScheduleBuilder.cronSchedule(cronExp))
                    .withIdentity(TriggerKey(jobName, TRIGGER_DEFAULT_GROUP_NAME)).build()
                scheduler!!.rescheduleJob(triggerKey, newTrigger)
            } else {
                log.warn(
                    "update job name:{},group name:{} or trigger name:{},group name:{} not exists..".plus(jobKey.name)
                        .plus(triggerKey.name).plus(triggerKey.group)
                )
            }
        } catch (e: SchedulerException) {
            log.warn("update job name:{},group name:{} failed!".plus(jobKey.name).plus(jobKey.group))
        }
    }

    /** 删除定时任务  */
    private fun deleteJob(jobName: String) {
        val jobKey = JobKey(jobName, JOB_DEFAULT_GROUP_NAME)
        try {
            if (scheduler!!.checkExists(jobKey)) {
                scheduler!!.deleteJob(jobKey)
            } else {
                log.warn(
                    "delete job name:{},group name:{} not exists.".plus(jobKey.name).plus(jobKey.group)
                )
            }
        } catch (e: SchedulerException) {
            log.warn("delete job name:{},group name:{} failed!".plus(jobKey.name).plus(jobKey.group))
        }
    }

    companion object {
        private val schedulerFactory: SchedulerFactory = StdSchedulerFactory()
        private const val JOB_DEFAULT_GROUP_NAME = "JOB_DEFAULT_GROUP_NAME"
        private const val TRIGGER_DEFAULT_GROUP_NAME = "TRIGGER_DEFAULT_GROUP_NAME"
    }
}

```