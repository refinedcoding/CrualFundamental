## 集群脑裂导致数据丢失怎么办？

1. 尽量避免脑裂发生
2. 尽量减少脑裂时的写入，例如master一定时间没收到心跳就不再接收client的新数据
