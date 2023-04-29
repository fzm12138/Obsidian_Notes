- Inter-Integrated Circuit
- 同步，半双工总线：
	- 发送接收严格同步，有同步时钟线
	- 只有一条数据线
---------------
##### 理念
- 信号线尽量少，速率要高
- 减少引脚占用
---------------
**SCL（Serial Clock）**：时钟线，时钟都是有master提供的  
**SDA（Serial Data）**：双向数据线，发数据或者收数据（收发不能同时）

###### 同一时刻只有一个master和一个slave通信
- 多个master-slave时钟，数据线连在一起，需要实现信号的“线”与逻辑
- 引脚在输出信号的同时还能对引脚上的电平进行检测，检测是否与刚才的输出一致
- I2C读写时要带上设备地址，这样不使用多的信号线就可以指定特地给的slave（SPI需要更多的片选线）
-------
##### I2C的读写
写：
1.  Master发起START
2.  Master发送I2C addr（7bit）和W(写)操作0（1bit），等待ACK
3.  Slave发送ACK
4.  Master发送reg addr（8bit），等待ACK
5.  Slave发送ACK
6.  Master发送data（8bit），即要写入寄存器中的数据，等待ACK
7.  Slave发送ACK  
    第6步和第7步可以重复多次，即顺序写多个寄存器
8.  Master发起STOP结束传输

读：
1.  Master发起START
2.  Master发送I2C addr（7bit）和r（读）操作1（1bit），等待ACK
3.  Slave发送ACK
4.  Slave发送data（8bit），即寄存器里的值
5.  Master发送ACK  
    第7步和第8步可以重复多次，即顺序读多个寄存器
6.  当master接收完想要的数据后，由Master发送NACK，告知slave停止发送数据
7.  Master发送STOP结束传输

- **实际上，I2C读过程之前要指定读取的寄存器地址，所以读过程之前需要master写寄存器的操作，告诉slave后面读取寄存器的起始地址**
- 完整的I2C读过程=写过程+读过程，其中涉及读写方向的转变









