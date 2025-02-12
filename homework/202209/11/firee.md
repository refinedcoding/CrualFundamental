### 讲讲 TCP 连接 6 种标识

1）SYN，简写 S，请求标志位，用来建立连接。在 TCP 三次握手中收到带有该标志位的数据包，表示对方想与己方建立连接；

2）ACK，简写【.】，请求确认/应答标志位，用于对对方的请求进行应答，对方收到含该标志位的数据包，会知道己方存在且可用。也会用在连接建立之后，己方发送响应数据给对方的数据包中；

3）FIN，简写 F，请求断开标志位，用于断开连接。对方收到己方的含该标志位的数据包，就知道己方想与它断开连接，不再保持连接；

4）RST，简写 R，请求复位标志位，因网络或己方服务原因导致有数据包丢失，己方接收到的数据包序列号与上一个数据包的序列号不衔接，那己方会发送含该标志位的数据包告诉对方，对方接收到含该标志位的数据包就知道己方要求它重新三次握手建立连接并重新发送丢失的数据包，一般断点续传会用到该标志位；

还有就是如果对方发过来的数据错了，有问题，己方也会发送含该标志位的数据包；

5）PSH，简写 P，推送标志位，表示收到数据包后要立即交给应用程序去处理，不应该放在缓存中，read()/write() 都有缓存区；

6）URG，简写 U，紧急标志位，该标志位表示 tcp 包首部中的紧急指针域有效，督促中间层尽快处理；

ref https://zhuanlan.zhihu.com/p/406247432
