为何一定要等2MSL？

- 如果不等，释放的端口可能会重连刚断开的服务器端口，这样依然存活在网络里的老的TCP报文可能与新TCP连接报文冲突，造成数据冲突。
- 为避免此种情况，需要等待老的TCP连接的活跃报文全部消失，而2MSL时间可以满足这个需求。
