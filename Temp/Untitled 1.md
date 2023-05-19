```java
2023-05-19 09:43:00
Full thread dump Java HotSpot(TM) 64-Bit Server VM (25.181-b13 mixed mode):

"schedule-pool-5" #78 daemon prio=5 os_prio=0 tid=0x00007f3c481c6000 nid=0x53f2 waiting on condition [0x00007f3be2c61000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceb94140> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1088)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Attach Listener" #77 daemon prio=9 os_prio=0 tid=0x00007f3c4c11e000 nid=0x4fe9 waiting on condition [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"schedule-pool-4" #76 daemon prio=5 os_prio=0 tid=0x00007f3c6020c800 nid=0x4ef5 waiting on condition [0x00007f3be2e63000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceb94140> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1088)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Thread-15" #75 prio=5 os_prio=0 tid=0x00007f3c885c8000 nid=0x4dc1 runnable [0x00007f3be2f64000]
   java.lang.Thread.State: RUNNABLE
	at java.security.AccessController.doPrivileged(Native Method)
	at java.net.Socket.getInputStream(Socket.java:911)
	at com.ruoyi.web.socket.ServerThread.run(SocketServer.java:122)

   Locked ownable synchronizers:
	- None

"schedule-pool-3" #74 daemon prio=5 os_prio=0 tid=0x00007f3c68018800 nid=0x4b27 waiting on condition [0x00007f3be3065000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceb94140> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1081)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Thread-14" #73 prio=5 os_prio=0 tid=0x00007f3c89f0e000 nid=0x48ca runnable [0x00007f3be3166000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.socketRead(SocketInputStream.java:116)
	at java.net.SocketInputStream.read(SocketInputStream.java:171)
	at java.net.SocketInputStream.read(SocketInputStream.java:141)
	at java.net.SocketInputStream.read(SocketInputStream.java:127)
	at com.ruoyi.web.ModeBusUtils.ModeBusUtils.readInputStream(ModeBusUtils.java:14)
	at com.ruoyi.web.socket.ServerThread.run(SocketServer.java:125)

   Locked ownable synchronizers:
	- None

"schedule-pool-2" #72 daemon prio=5 os_prio=0 tid=0x00007f3c600d2000 nid=0x428c waiting on condition [0x00007f3be3467000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceb94140> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1081)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

  Locked ownable synchronizers:
	- None

"Thread-13" #71 prio=5 os_prio=0 tid=0x00007f3c89f0d000 nid=0x41d5 runnable [0x00007f3be3568000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.socketRead(SocketInputStream.java:116)
	at java.net.SocketInputStream.read(SocketInputStream.java:171)
	at java.net.SocketInputStream.read(SocketInputStream.java:141)
	at java.net.SocketInputStream.read(SocketInputStream.java:127)
	at com.ruoyi.web.ModeBusUtils.ModeBusUtils.readInputStream(ModeBusUtils.java:14)
	at com.ruoyi.web.socket.ServerThread.run(SocketServer.java:125)

   Locked ownable synchronizers:
	- None

"schedule-pool-1" #70 daemon prio=5 os_prio=0 tid=0x0000000000d5f000 nid=0x3f6c waiting on condition [0x00007f3be3869000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceb94140> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1081)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Java2D Disposer" #68 daemon prio=10 os_prio=0 tid=0x00007f3c6002a800 nid=0x3f5b in Object.wait() [0x00007f3be85a7000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:144)
	- locked <0x00000006cf79f3a8> (a java.lang.ref.ReferenceQueue$Lock)
	at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:165)
	at sun.java2d.Disposer.run(Disposer.java:148)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-10" #67 daemon prio=5 os_prio=0 tid=0x00007f3c349b2800 nid=0x3cf1 waiting on condition [0x00007f3be8f81000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Thread-11" #66 prio=5 os_prio=0 tid=0x00007f3c8884d800 nid=0x3ced runnable [0x00007f3be9082000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.socketRead(SocketInputStream.java:116)
	at java.net.SocketInputStream.read(SocketInputStream.java:171)
	at java.net.SocketInputStream.read(SocketInputStream.java:141)
	at java.net.SocketInputStream.read(SocketInputStream.java:127)
	at com.ruoyi.web.ModeBusUtils.ModeBusUtils.readInputStream(ModeBusUtils.java:14)
	at com.ruoyi.web.socket.ServerThread.run(SocketServer.java:125)

   Locked ownable synchronizers:
	- None

"Thread-10" #65 prio=5 os_prio=0 tid=0x00007f3c88354000 nid=0x3cec runnable [0x00007f3be9183000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.socketRead(SocketInputStream.java:116)
	at java.net.SocketInputStream.read(SocketInputStream.java:171)
	at java.net.SocketInputStream.read(SocketInputStream.java:141)
	at java.net.SocketInputStream.read(SocketInputStream.java:127)
	at com.ruoyi.web.ModeBusUtils.ModeBusUtils.readInputStream(ModeBusUtils.java:14)
	at com.ruoyi.web.socket.ServerThread.run(SocketServer.java:125)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-9" #64 daemon prio=5 os_prio=0 tid=0x00007f3c3462e000 nid=0x3cd9 waiting on condition [0x00007f3be9284000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-8" #63 daemon prio=5 os_prio=0 tid=0x00007f3c3462a800 nid=0x3cd8 waiting on condition [0x00007f3be9385000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-7" #62 daemon prio=5 os_prio=0 tid=0x00007f3c34125800 nid=0x3cd7 waiting on condition [0x00007f3be9486000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-6" #61 daemon prio=5 os_prio=0 tid=0x00007f3c347a2000 nid=0x3cd6 waiting on condition [0x00007f3be9587000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-5" #60 daemon prio=5 os_prio=0 tid=0x00007f3c34014000 nid=0x3cd2 waiting on condition [0x00007f3be9688000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-4" #59 daemon prio=5 os_prio=0 tid=0x00007f3c34a01000 nid=0x3cd1 waiting on condition [0x00007f3be9c8c000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"QuartzScheduler_RuoyiScheduler-iZ2zedu6dhs2nmmf0v6brzZ1684458363793_MisfireHandler" #58 prio=5 os_prio=0 tid=0x00007f3c5400d000 nid=0x3ccf waiting on condition [0x00007f3be9789000]
   java.lang.Thread.State: TIMED_WAITING (sleeping)
	at java.lang.Thread.sleep(Native Method)
	at org.quartz.impl.jdbcjobstore.JobStoreSupport$MisfireHandler.run(JobStoreSupport.java:4053)

   Locked ownable synchronizers:
	- None

"QuartzScheduler_RuoyiScheduler-iZ2zedu6dhs2nmmf0v6brzZ1684458363793_ClusterManager" #57 prio=7 os_prio=0 tid=0x00007f3c5400b800 nid=0x3cce waiting on condition [0x00007f3be988a000]
   java.lang.Thread.State: TIMED_WAITING (sleeping)
	at java.lang.Thread.sleep(Native Method)
	at org.quartz.impl.jdbcjobstore.JobStoreSupport$ClusterManager.run(JobStoreSupport.java:3967)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-3" #56 daemon prio=5 os_prio=0 tid=0x00007f3c34a25800 nid=0x3ccd waiting on condition [0x00007f3be998b000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-2" #54 daemon prio=5 os_prio=0 tid=0x00007f3c348c7000 nid=0x3cc8 waiting on condition [0x00007f3be9f8d000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-exec-1" #53 daemon prio=5 os_prio=0 tid=0x00007f3c3479c000 nid=0x3cc7 waiting on condition [0x00007f3bea4e9000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006ceffb830> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:146)
	at org.apache.tomcat.util.threads.TaskQueue.take(TaskQueue.java:33)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1114)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1176)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-Acceptor" #52 daemon prio=5 os_prio=0 tid=0x00007f3c893af800 nid=0x3cc4 runnable [0x00007f3bea5ea000]
   java.lang.Thread.State: RUNNABLE
	at sun.nio.ch.ServerSocketChannelImpl.accept0(Native Method)
	at sun.nio.ch.ServerSocketChannelImpl.accept(ServerSocketChannelImpl.java:422)
	at sun.nio.ch.ServerSocketChannelImpl.accept(ServerSocketChannelImpl.java:250)
	- locked <0x00000006cf04ea90> (a java.lang.Object)
	at org.apache.tomcat.util.net.NioEndpoint.serverSocketAccept(NioEndpoint.java:540)
	at org.apache.tomcat.util.net.NioEndpoint.serverSocketAccept(NioEndpoint.java:78)
	at org.apache.tomcat.util.net.Acceptor.run(Acceptor.java:106)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"http-nio-8080-Poller" #51 daemon prio=5 os_prio=0 tid=0x00007f3c893ab800 nid=0x3cc3 runnable [0x00007f3bea6eb000]
   java.lang.Thread.State: RUNNABLE
	at sun.nio.ch.EPollArrayWrapper.epollWait(Native Method)
	at sun.nio.ch.EPollArrayWrapper.poll(EPollArrayWrapper.java:269)
	at sun.nio.ch.EPollSelectorImpl.doSelect(EPollSelectorImpl.java:93)
	at sun.nio.ch.SelectorImpl.lockAndDoSelect(SelectorImpl.java:86)
	- locked <0x00000006cf04e300> (a sun.nio.ch.Util$3)
	- locked <0x00000006cf04e2f0> (a java.util.Collections$UnmodifiableSet)
	- locked <0x00000006ceffbc80> (a sun.nio.ch.EPollSelectorImpl)
	at sun.nio.ch.SelectorImpl.select(SelectorImpl.java:97)
	at org.apache.tomcat.util.net.NioEndpoint$Poller.run(NioEndpoint.java:787)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"MQTT Ping: ccb337ed-dd4f-43d6-9655-5fa08d94a079" #50 prio=5 os_prio=0 tid=0x00007f3c24464000 nid=0x3cc0 in Object.wait() [0x00007f3beacef000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.util.TimerThread.mainLoop(Timer.java:552)
	- locked <0x00000006cece3fe8> (a java.util.TaskQueue)
	at java.util.TimerThread.run(Timer.java:505)

   Locked ownable synchronizers:
	- None

"MQTT Call: ccb337ed-dd4f-43d6-9655-5fa08d94a079" #49 prio=5 os_prio=0 tid=0x00007f3c28050800 nid=0x3cbe in Object.wait() [0x00007f3bea9ec000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.Object.wait(Object.java:502)
	at org.eclipse.paho.client.mqttv3.internal.CommsCallback.run(CommsCallback.java:181)
	- locked <0x00000006cece3cf0> (a java.lang.Object)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"MQTT Snd: ccb337ed-dd4f-43d6-9655-5fa08d94a079" #48 prio=5 os_prio=0 tid=0x00007f3c28029000 nid=0x3cbd in Object.wait() [0x00007f3beaaed000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.Object.wait(Object.java:502)
	at org.eclipse.paho.client.mqttv3.internal.ClientState.get(ClientState.java:833)
	- locked <0x00000006cece3da0> (a java.lang.Object)
	at org.eclipse.paho.client.mqttv3.internal.CommsSender.run(CommsSender.java:129)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"MQTT Rec: ccb337ed-dd4f-43d6-9655-5fa08d94a079" #47 prio=5 os_prio=0 tid=0x00007f3c2800f000 nid=0x3cba runnable [0x00007f3beabee000]
   java.lang.Thread.State: RUNNABLE
	at java.net.SocketInputStream.socketRead0(Native Method)
	at java.net.SocketInputStream.socketRead(SocketInputStream.java:116)
	at java.net.SocketInputStream.read(SocketInputStream.java:171)
	at java.net.SocketInputStream.read(SocketInputStream.java:141)
	at java.net.SocketInputStream.read(SocketInputStream.java:224)
	at java.io.DataInputStream.readByte(DataInputStream.java:265)
	at org.eclipse.paho.client.mqttv3.internal.wire.MqttInputStream.readMqttWireMessage(MqttInputStream.java:92)
	at org.eclipse.paho.client.mqttv3.internal.CommsReceiver.run(CommsReceiver.java:137)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_QuartzSchedulerThread" #45 prio=5 os_prio=0 tid=0x00007f3c89f4e000 nid=0x3cb3 in Object.wait() [0x00007f3beb1f0000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.core.QuartzSchedulerThread.run(QuartzSchedulerThread.java:427)
	- locked <0x00000006cddb7cb0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-20" #44 prio=5 os_prio=0 tid=0x00007f3c89f36000 nid=0x3cb2 in Object.wait() [0x00007f3beb2f1000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb76c0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-19" #43 prio=5 os_prio=0 tid=0x00007f3c89f34000 nid=0x3cb1 in Object.wait() [0x00007f3beb3f2000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb5a60> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-18" #42 prio=5 os_prio=0 tid=0x00007f3c89f32000 nid=0x3cb0 in Object.wait() [0x00007f3beb4f3000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb5770> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-17" #41 prio=5 os_prio=0 tid=0x00007f3c89f30000 nid=0x3caf in Object.wait() [0x00007f3beb5f4000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb5480> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-16" #40 prio=5 os_prio=0 tid=0x00007f3c89f2e000 nid=0x3cae in Object.wait() [0x00007f3beb6f5000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb5190> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-15" #39 prio=5 os_prio=0 tid=0x00007f3c89f2c000 nid=0x3cad in Object.wait() [0x00007f3beb7f6000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb4ea0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-14" #38 prio=5 os_prio=0 tid=0x00007f3c89f2a000 nid=0x3cac in Object.wait() [0x00007f3beb8f7000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb4bb0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-13" #37 prio=5 os_prio=0 tid=0x00007f3c89f28000 nid=0x3cab in Object.wait() [0x00007f3beb9f8000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb48c0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-12" #36 prio=5 os_prio=0 tid=0x00007f3c89f26000 nid=0x3caa in Object.wait() [0x00007f3bebaf9000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb45d0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-11" #35 prio=5 os_prio=0 tid=0x00007f3c89f24000 nid=0x3ca9 in Object.wait() [0x00007f3bebbfa000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb42e0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-10" #34 prio=5 os_prio=0 tid=0x00007f3c89f22800 nid=0x3ca8 in Object.wait() [0x00007f3bebcfb000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb3ff0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-9" #33 prio=5 os_prio=0 tid=0x00007f3c89f20800 nid=0x3ca7 in Object.wait() [0x00007f3bebdfc000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb1d40> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-8" #32 prio=5 os_prio=0 tid=0x00007f3c89f1e800 nid=0x3ca6 in Object.wait() [0x00007f3bebefd000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb1a50> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-7" #31 prio=5 os_prio=0 tid=0x00007f3c89f1c800 nid=0x3ca5 in Object.wait() [0x00007f3bebffe000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb1760> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-6" #30 prio=5 os_prio=0 tid=0x00007f3c89f1a800 nid=0x3ca4 in Object.wait() [0x00007f3c401b5000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb1470> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-5" #29 prio=5 os_prio=0 tid=0x00007f3c89f18800 nid=0x3ca3 in Object.wait() [0x00007f3c402b6000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb1180> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-4" #28 prio=5 os_prio=0 tid=0x00007f3c89f16800 nid=0x3ca2 in Object.wait() [0x00007f3c403b7000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb0e90> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-3" #27 prio=5 os_prio=0 tid=0x00007f3c89f14800 nid=0x3ca1 in Object.wait() [0x00007f3c404b8000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb0ba0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-2" #26 prio=5 os_prio=0 tid=0x00007f3c89f12800 nid=0x3ca0 in Object.wait() [0x00007f3c405b9000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb08b0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"RuoyiScheduler_Worker-1" #25 prio=5 os_prio=0 tid=0x00007f3c89f11000 nid=0x3c9f in Object.wait() [0x00007f3c406ba000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:568)
	- locked <0x00000006cddb05c0> (a java.lang.Object)

   Locked ownable synchronizers:
	- None

"lettuce-eventExecutorLoop-1-4" #24 daemon prio=5 os_prio=0 tid=0x00007f3c89a92000 nid=0x3c90 waiting on condition [0x00007f3c64178000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd03e3e8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at io.netty.util.concurrent.SingleThreadEventExecutor.takeTask(SingleThreadEventExecutor.java:243)
	at io.netty.util.concurrent.DefaultEventExecutor.run(DefaultEventExecutor.java:64)
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:986)
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"lettuce-eventExecutorLoop-1-3" #23 daemon prio=5 os_prio=0 tid=0x00007f3c89a90000 nid=0x3c8f waiting on condition [0x00007f3c64279000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd023eb8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at io.netty.util.concurrent.SingleThreadEventExecutor.takeTask(SingleThreadEventExecutor.java:243)
	at io.netty.util.concurrent.DefaultEventExecutor.run(DefaultEventExecutor.java:64)
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:986)
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"lettuce-eventExecutorLoop-1-2" #22 daemon prio=5 os_prio=0 tid=0x00007f3c89a8e800 nid=0x3c8e waiting on condition [0x00007f3c6437a000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd03dfe8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at io.netty.util.concurrent.SingleThreadEventExecutor.takeTask(SingleThreadEventExecutor.java:243)
	at io.netty.util.concurrent.DefaultEventExecutor.run(DefaultEventExecutor.java:64)
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:986)
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"lettuce-eventExecutorLoop-1-1" #21 daemon prio=5 os_prio=0 tid=0x00007f3c8929f800 nid=0x3c8d waiting on condition [0x00007f3c6447b000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd03e1e8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.LinkedBlockingQueue.take(LinkedBlockingQueue.java:442)
	at io.netty.util.concurrent.SingleThreadEventExecutor.takeTask(SingleThreadEventExecutor.java:243)
	at io.netty.util.concurrent.DefaultEventExecutor.run(DefaultEventExecutor.java:64)
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:986)
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"lettuce-nioEventLoop-4-1" #20 daemon prio=5 os_prio=0 tid=0x00007f3c8988d000 nid=0x3c8b runnable [0x00007f3c6477c000]
   java.lang.Thread.State: RUNNABLE
	at sun.nio.ch.EPollArrayWrapper.epollWait(Native Method)
	at sun.nio.ch.EPollArrayWrapper.poll(EPollArrayWrapper.java:269)
	at sun.nio.ch.EPollSelectorImpl.doSelect(EPollSelectorImpl.java:93)
	at sun.nio.ch.SelectorImpl.lockAndDoSelect(SelectorImpl.java:86)
	- locked <0x00000006cdc37668> (a io.netty.channel.nio.SelectedSelectionKeySet)
	- locked <0x00000006cdd1d1d0> (a java.util.Collections$UnmodifiableSet)
	- locked <0x00000006cdc37680> (a sun.nio.ch.EPollSelectorImpl)
	at sun.nio.ch.SelectorImpl.select(SelectorImpl.java:97)
	at sun.nio.ch.SelectorImpl.select(SelectorImpl.java:101)
	at io.netty.channel.nio.SelectedSelectionKeySetSelector.select(SelectedSelectionKeySetSelector.java:68)
	at io.netty.channel.nio.NioEventLoop.select(NioEventLoop.java:810)
	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:457)
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:986)
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Druid-ConnectionPool-Destroy-334593716" #19 daemon prio=5 os_prio=0 tid=0x00007f3c882a9000 nid=0x3c86 waiting on condition [0x00007f3c64e7d000]
   java.lang.Thread.State: TIMED_WAITING (sleeping)
	at java.lang.Thread.sleep(Native Method)
	at com.alibaba.druid.pool.DruidDataSource$DestroyConnectionThread.run(DruidDataSource.java:2913)

   Locked ownable synchronizers:
	- None

"Druid-ConnectionPool-Create-334593716" #18 daemon prio=5 os_prio=0 tid=0x00007f3c882a8000 nid=0x3c85 waiting on condition [0x00007f3c64f7e000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd4ee6d0> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at com.alibaba.druid.pool.DruidDataSource$CreateConnectionThread.run(DruidDataSource.java:2813)

   Locked ownable synchronizers:
	- None

"mysql-cj-abandoned-connection-cleanup" #17 daemon prio=5 os_prio=0 tid=0x00007f3c89c88000 nid=0x3c81 in Object.wait() [0x00007f3c65adc000]
   java.lang.Thread.State: TIMED_WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:144)
	- locked <0x00000006cd6d1490> (a java.lang.ref.ReferenceQueue$Lock)
	at com.mysql.cj.jdbc.AbandonedConnectionCleanupThread.run(AbandonedConnectionCleanupThread.java:91)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- <0x00000006cd6056d0> (a java.util.concurrent.ThreadPoolExecutor$Worker)

"container-0" #16 prio=5 os_prio=0 tid=0x00007f3c89c6a800 nid=0x3c76 waiting on condition [0x00007f3c65fdd000]
   java.lang.Thread.State: TIMED_WAITING (sleeping)
	at java.lang.Thread.sleep(Native Method)
	at org.apache.catalina.core.StandardServer.await(StandardServer.java:563)
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer$1.run(TomcatWebServer.java:197)

   Locked ownable synchronizers:
	- None

"Catalina-utility-2" #15 prio=1 os_prio=0 tid=0x00007f3c89c60800 nid=0x3c75 waiting on condition [0x00007f3c67efd000]
   java.lang.Thread.State: WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd0754d8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.park(LockSupport.java:175)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2039)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1088)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Catalina-utility-1" #14 prio=1 os_prio=0 tid=0x00007f3c89c54800 nid=0x3c74 waiting on condition [0x00007f3c67ffe000]
   java.lang.Thread.State: TIMED_WAITING (parking)
	at sun.misc.Unsafe.park(Native Method)
	- parking to wait for  <0x00000006cd0754d8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
	at java.util.concurrent.locks.LockSupport.parkNanos(LockSupport.java:215)
	at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.awaitNanos(AbstractQueuedSynchronizer.java:2078)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:1093)
	at java.util.concurrent.ScheduledThreadPoolExecutor$DelayedWorkQueue.take(ScheduledThreadPoolExecutor.java:809)
	at java.util.concurrent.ThreadPoolExecutor.getTask(ThreadPoolExecutor.java:1074)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1134)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"lettuce-timer-3-1" #13 daemon prio=5 os_prio=0 tid=0x00007f3c88d7a000 nid=0x3c71 waiting on condition [0x00007f3c6c62c000]
   java.lang.Thread.State: TIMED_WAITING (sleeping)
	at java.lang.Thread.sleep(Native Method)
	at io.netty.util.HashedWheelTimer$Worker.waitForNextTick(HashedWheelTimer.java:600)
	at io.netty.util.HashedWheelTimer$Worker.run(HashedWheelTimer.java:496)
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	at java.lang.Thread.run(Thread.java:748)

   Locked ownable synchronizers:
	- None

"Service Thread" #8 daemon prio=9 os_prio=0 tid=0x00007f3c88199800 nid=0x3c58 runnable [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"C1 CompilerThread2" #7 daemon prio=9 os_prio=0 tid=0x00007f3c88184800 nid=0x3c57 waiting on condition [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"C2 CompilerThread1" #6 daemon prio=9 os_prio=0 tid=0x00007f3c88182800 nid=0x3c56 waiting on condition [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"C2 CompilerThread0" #5 daemon prio=9 os_prio=0 tid=0x00007f3c8817f800 nid=0x3c55 waiting on condition [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"Signal Dispatcher" #4 daemon prio=9 os_prio=0 tid=0x00007f3c8817e000 nid=0x3c54 runnable [0x0000000000000000]
   java.lang.Thread.State: RUNNABLE

   Locked ownable synchronizers:
	- None

"Finalizer" #3 daemon prio=8 os_prio=0 tid=0x00007f3c8814b000 nid=0x3c53 in Object.wait() [0x00007f3c6da53000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:144)
	- locked <0x00000006cc12bb90> (a java.lang.ref.ReferenceQueue$Lock)
	at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:165)
	at java.lang.ref.Finalizer$FinalizerThread.run(Finalizer.java:216)

   Locked ownable synchronizers:
	- None

"Reference Handler" #2 daemon prio=10 os_prio=0 tid=0x00007f3c88146800 nid=0x3c52 in Object.wait() [0x00007f3c6db54000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at java.lang.Object.wait(Object.java:502)
	at java.lang.ref.Reference.tryHandlePending(Reference.java:191)
	- locked <0x00000006cc21d078> (a java.lang.ref.Reference$Lock)
	at java.lang.ref.Reference$ReferenceHandler.run(Reference.java:153)

   Locked ownable synchronizers:
	- None

"main" #1 prio=5 os_prio=0 tid=0x00007f3c88009000 nid=0x3c4c runnable [0x00007f3c8e5be000]
   java.lang.Thread.State: RUNNABLE
	at java.net.PlainSocketImpl.socketAccept(Native Method)
	at java.net.AbstractPlainSocketImpl.accept(AbstractPlainSocketImpl.java:409)
	at java.net.ServerSocket.implAccept(ServerSocket.java:545)
	at java.net.ServerSocket.accept(ServerSocket.java:513)
	at com.ruoyi.web.socket.SocketServer.start(SocketServer.java:41)
	at com.ruoyi.RuoYiApplication.main(RuoYiApplication.java:32)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.springframework.boot.loader.MainMethodRunner.run(MainMethodRunner.java:48)
	at org.springframework.boot.loader.Launcher.launch(Launcher.java:87)
	at org.springframework.boot.loader.Launcher.launch(Launcher.java:50)
	at org.springframework.boot.loader.JarLauncher.main(JarLauncher.java:51)

   Locked ownable synchronizers:
	- None

"VM Thread" os_prio=0 tid=0x00007f3c8813e800 nid=0x3c51 runnable 

"GC task thread#0 (ParallelGC)" os_prio=0 tid=0x00007f3c8801e800 nid=0x3c4d runnable 

"GC task thread#1 (ParallelGC)" os_prio=0 tid=0x00007f3c88020800 nid=0x3c4e runnable 

"GC task thread#2 (ParallelGC)" os_prio=0 tid=0x00007f3c88022000 nid=0x3c4f runnable 

"GC task thread#3 (ParallelGC)" os_prio=0 tid=0x00007f3c88024000 nid=0x3c50 runnable 

"VM Periodic Task Thread" os_prio=0 tid=0x00007f3c8819e800 nid=0x3c59 waiting on condition 

JNI global references: 2890


```