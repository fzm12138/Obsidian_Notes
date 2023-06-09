```kotlin

import lombok.Getter
import lombok.extern.slf4j.Slf4j
import org.hibernate.query.sqm.tree.SqmNode.log
import org.quartz.Job
import org.quartz.JobExecutionContext

/**
 * @author fzm
 * @since 2023-06-08
 * **/
@Slf4j
@Getter
abstract class AbstractTask : Job {

    var cronExpression: String? = null
    protected abstract fun executeInternal(context: JobExecutionContext?)

    override fun execute(context: JobExecutionContext?) {
        try {
            println("execute of AbstractTask")
            executeInternal(context)
        } catch (e: Exception) {
            log.warn("job execute failed.", e)
        }
    }
}
```