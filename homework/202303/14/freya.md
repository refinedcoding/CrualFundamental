## 重传机制

TCP的重传机制有：

- 超时重传：对于发送的数据，有一个计时器，当超过指定的时间后就会重新发送数据

- 快速重传：同时发送多个数据，例如1、2、3，但收到多次ack=2的确认，则说明2大概率丢失，马上重传2