![[Unity架构3_0.png]]

需要的技能：
- Unity开发
- 网络通信
- 数据库
- 服务器架构与开发
- 服务器运维

#### 实现过程：
- 加工设备安装IOT设备，IOT获取PLC数据以JSON格式实时上传
- 可以编写一个接收数据的后端服务，接收IOT上传的数据
- Unity通过HTTP或者Socket方式从服务器实时获取数据
- 通过实时获取的数据，在Untiy中实时对映射的虚拟设备（手动建模）驱动
- 如果需要反向控制，则
	- Unity发出命令，服务接收命令
	- IOT获取命令给PLC控制物理设备
-----
#### Unity相关插件：
###### 模型从CAD到Unity的转换
- CAD数据模型处理工具Pixyz
###### 数据通信
- PREspective
	- 提供多种工业通信协议接口
	- 复杂物理碰撞仿真
	- 网格合并，物体单选工具
	- 机械仿真工具
	- 接入物理仿真模型文件
		- Matlab、Anasys等
###### 功能性快速开发工具
- InterAct

###### 一键转换BIM数据到实时3D环境
- Reflect

###### 快速AR、VR开发
- MARS

-----
#### 解决方案
- CAD模型数据通过Pixyz转到Unity
- 物理设备PLC通过PREspective工具通信和定义行为，使得PLC数据实时传输到Unity驱动虚拟设备(此过程借助InterAct等工具)
- Unity发布成所需要的平台
![[Pasted image 20230429143319.png]]