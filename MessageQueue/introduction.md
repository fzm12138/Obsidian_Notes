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
- 