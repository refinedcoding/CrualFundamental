### TCP 拥塞控制？慢启动的时候窗口在什么情况下会增长？为什么会呈指数增长？

TCP拥塞控制：防止过多的数据注入网络，导致路由器或者链路过载。目标是为了让网络能够承受当前负载。

拥塞窗口增长：每当发送方收到一个ACK拥塞窗口cwnd会+1

为什么呈现指数：

假设拥塞窗口cwnd和接收窗口swnd。

```
连接建立完成后，开始初始化cwnd=1 传一个MSS大小数据
收到1个ACK, cwnd+1，一次可以发送2个
当收到2个ack确认后，cwnd增加2, 可以发送比之前多2个 因此可以发4个
4个ack确认收到后，每个ack可以使得cwnd增加1，因此4+4=8因此可以发送8个
```

就呈现出来指数性增长。



PS：到达慢启动门限使用拥塞避免算法。拥塞避免以后。每当收到1个ack cwnd增加1/cwnd。因此就变成了线性增长。

```
例如8个ack到达，拥塞避免，则每个ack增加1/8，因此一共增加1，可以发送9个mss大小，进入拥塞避免。
```

