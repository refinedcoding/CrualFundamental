## 为什么TIME_WAIT等待时间是2MSL？

MSL是报文最大生存时间，TIME_WAIT等待2个MSL，是因为网络中可能存在来自发送方的数据包，而当这些数据包被接收方处理后又会向对方发送响应，所以有两个来回，需要等待两个MSL。