### Why using this tech?
- Master-Slave DB & read-write seperate be used together always
- The purpose is improve DB's concurrency's performance

## The theory of it
- When ***MasterDB*** opreating `insert` `update` `delete` will wirte them in binlog in order.
- ***SlaveDB*** connect ***MasterDB*** and ***MasterDB*** creates as many binlog dump process as ***slaveDB***
- When ***MasterDB's*** binlog changes,binlog dump process will notice all ***SlvaeDB*** and then push the binlog to ***SlaveDB***
- I/O process receives binlog and write them into local's relay-log
- SQL process read relay-log and according to the contents of the relay-log to opreate ***SlaveDB***

## How to manage Master-Slave copy
1. Entering mysql and create users
```mysql
//192.168.0.106是slave从机的IP
GRANT REPLICATION SLAVE ON *.* to 'root'@'192.168.0.106' identified by 'Java@1234';
//192.168.0.107是slave从机的IP
GRANT REPLICATION SLAVE ON *.* to 'root'@'192.168.0.107' identified by 'Java@1234';
//刷新系统权限表的配置
FLUSH PRIVILEGES;
```
2. Find `my.cnf`
```mysql
# 开启binlog
log-bin=mysql-bin
server-id=104
# 需要同步的数据库，如果不配置则同步全部数据库
binlog-do-db=test_db
# binlog日志保留的天数，清除超过10天的日志
# 防止日志文件过大，导致磁盘空间不足
expire-logs-days=10 
```
3.Then restart mysql `service mysql restart`
4.could use `show master status\G` to check out what's in binlog
5.Slave's config
- find my.cnf and add 
```mysql
# 不要和其他mysql服务id重复即可
server-id=106
```
- login `mysql -u root -p`
```mysql
CHANGE MASTER TO 
MASTER_HOST='192.168.0.104',//主机IP
MASTER_USER='root',//之前创建的用户账号
MASTER_PASSWORD='Java@1234',//之前创建的用户密码
MASTER_LOG_FILE='mysql-bin.000001',//master主机的binlog日志名称
MASTER_LOG_POS=862,//binlog日志偏移量
master_port=3306;//端口
```
- Start Slave
```mysql
# 启动slave服务
start slave;
```

