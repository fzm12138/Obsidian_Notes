```yml
server:
  #设备向中转服务推送图片等
  port: 8087

logging:
  level:
    com.insectSituation.controller: INFO

spring:
  servlet:
    multipart:
      #不限制文件上传的大小，设置为-1
      #单个文件的大小
      max-file-size: 256MB
      #单次请求的文件的总大小
      max-request-size: 1024MB


knife4j:
  #是否开启Knife4j增强模式
  enable: true
  #设置密码
  basic:
    enable: true
    username: test
    password: 12313


analyzer:
  #通讯端口 (int类型,设备与中转服务通信)
  deviceConnectPort: 8045
  #图片上传位置
  imageFilePath: /usr/local/rkbugs
  #推送地址(向dsdigital服务)
  notifyUrlBase: http://localhost:8087
  #图片上传推送
  imageUploadNotifyUrl: /sdk/fileAddress
  #登录帧
  deviceLoginNotifyUrl: /sdk/login
  #实时数据帧
  deviceRealTimeDataNotifyUrl : /sdk/realTimeData
  #控制指令应答帧
  deviceCtrlResultNotifyUrl: /sdk/ctrl
  #设备参数应答帧
  deviceReceiveDataNotifyUrl: /sdk/receive
  #数据透传应答帧
  deviceTransDataNotifyUrl: /sdk/trans
```

### 实际需要修改的部分
- 将以下部分修改成符合我们实际需求的
```yml
server:
  #设备向中转服务推送图片等
  port: 8087
  
analyzer:
  #通讯端口 (int类型,设备与中转服务通信)
  deviceConnectPort: 8045
  #图片上传位置
  imageFilePath: /usr/local/rkbugs
  #推送地址(向dsdigital服务)
  notifyUrlBase: http://localhost:8087
  #图片上传推送
```

### 虫情设备需要的准备
- 检查sim卡是否到期，是否有流量
- 检查虫情设备是否能连上仁科的平台
- 修改`设备目标端口` 与yml文件中的通讯端口一致
- 修改`图片上传端口` 与server的端口一致
	- 都设置为8087
- 将图片上传位置设置为自己服务器上的文件夹
- 将推送地址设为我们自己的服务想访问的端口
	- 中转服务与我们平台通过此端口通信

### 需要修改的yml文件在/resources下
`application.yml`

