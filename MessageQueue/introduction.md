The common meaasge Queue:
- kafka, ActiveMQ, RabbitMQ, RocketMQ

### kafka 
- Distributed publish-subscription system
- Written by `Java` and `Scala`
- it's for high throughput and subsciption
- Massage is build up by *key、value、timestamp*
- kafka works through Hadoop
###### The features of kafka
- Persistence is supported  by a kind of disk-data-stucture,the very stucture could keep high-effensive for a long time when TB level massgages needs to be storage
- High throughput: Even odinary hardware could support kafka 
- Supports millions/s 
- support Hadoop
### RabbitMQ
- Developed by Erlang and it's **opensource**
- Basic on AMQP
	- AMQP: message oriented, queue,routing, reliable and safe
	- using in the scences wich demends consistency,reliable and safe,then purse performance and throughput
###### The features of RabbitMQ
- Reliablity : supported by persistence，transport/publishack
- Flexible Routing : before massages get in to the queue , using `Excahnge` to routing massages->
	- For typical routing functions ,RBMQ suplies some built-in Exchange
	- For comlex routing funtions could bond multiple Exchange or using plugin mechanism implents own Exchange 
- Clustering : multiple server build-up a clustering forms a logic Broker
- Highly Avaliable Queues : queues could make iso on clustering then it could work when some nodes couldn't work
- Muti-protocol :RBMQ supports STOMP,MQTT
- Many clients : RBMQ supports almost all the common languages