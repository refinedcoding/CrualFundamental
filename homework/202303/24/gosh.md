HTTPS中的TLS和TCP能同时握手吗

正常情况下，先TCP三次握手，再TLS四次握手

TLS的握手次数还要看版本：
	TLSv1.2握手过程要四次（2-RTT）
	TLSv1.3握手过程只用两次（1-RTT）

一般情况下，不管TLS握手次数如何，都要先经过TCP三次握手后才能进行，因为HTTPS是基于TCP传输协议实现的，要先建立完可靠的TCP连接才能做TLS握手的事情。

特殊情况：
客户端和服务端都开启了TCP Fast Open功能，且TLS版本是1.3
客户端和服务端已经完成过一次通信

TCP Fast Open， 利用Cookie，使得第一次连接成功之后的连接可以在第一次握手时就传送数据
此时在第一次握手的同时进行TLSv1.3握手，就可以做到 0-RTT