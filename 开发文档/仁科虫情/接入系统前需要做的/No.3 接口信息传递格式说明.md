### 接口调用
- HTTP协议
- 接口以json格式传输数据
- 接口信息编码格式为utf-8

- 中转服务提供的返回数据均为`ResultData`格式
	- 返回的数据存在data字段中
eg: 
```json
{"code":1000, "message":"信息内容", "data":object} 
```

```json
code : Integer, 参考代码返回说明表
message: String,返回操作结果描述
data: Json, 格式参考接口
```

- post方法接口中为json格式
- get方法接口中参数为查询参数
	- *放入请求地址后*
- 控制设备接口中转服务调用
- 通知接口在设备应答后推送数据
	- 需要客户实现接口
