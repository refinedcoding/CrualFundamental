发送方发送数据时需要考虑接收方的接受能力，因此需要进行流量控制。

发送方会维护一个发送窗口，而接收方也会维护一个接收窗口，发送方发送完数据后，会收到窗口为x的应答，动态地维护窗口大小。