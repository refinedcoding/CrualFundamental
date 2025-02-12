Quic 全称 quick udp internet connection ，“快速 UDP 互联网连接”，（和英文 quick 谐音，简称“快”）是由 google 提出的使用 udp 进行多路并发传输的协议。

Quic 相比现在广泛应用的 http2+tcp+tls 协议有如下优势 ：

减少了 TCP 三次握手及 TLS 握手时间。
改进的拥塞控制。
避免队头阻塞的多路复用。
连接迁移。
前向冗余纠错。

从上个世纪 90 年代互联网开始兴起一直到现在，大部分的互联网流量传输只使用了几个网络协议。使用 IPv4 进行路由，使用 TCP 进行连接层面的流量控制，使用 SSL/TLS 协议实现传输安全，使用 DNS 进行域名解析，使用 HTTP 进行应用数据的传输。

而且近三十年来，这几个协议的发展都非常缓慢。TCP 主要是拥塞控制算法的改进，SSL/TLS 基本上停留在原地，几个小版本的改动主要是密码套件的升级，TLS1.3[3] 是一个飞跃式的变化，但截止到今天，还没有正式发布。IPv4 虽然有一个大的进步，实现了 IPv6，DNS 也增加了一个安全的 DNSSEC，但和 IPv6 一样，部署进度较慢。

一方面是历史悠久使用广泛的古老协议，另外一方面用户的使用场景对传输性能的要求又越来越高。如下几个由来已久的问题和矛盾就变得越来越突出。

协议历史悠久导致中间设备僵化。
依赖于操作系统的实现导致协议本身僵化。
建立连接的握手延迟大。
队头阻塞。

建立连接的握手延迟大

不管是 HTTP1.0/1.1 还是 HTTPS，HTTP2，都使用了 TCP 进行传输。HTTPS 和 HTTP2 还需要使用 TLS 协议来进行安全传输。这就出现了两个握手延迟：
1.TCP 三次握手导致的 TCP 连接建立的延迟。

2.TLS 完全握手需要至少 2 个 RTT 才能建立，简化握手需要 1 个 RTT 的握手延迟。

对于很多短连接场景，这样的握手延迟影响很大，且无法消除。

队头阻塞

队头阻塞主要是 TCP 协议的可靠性机制引入的。TCP 使用序列号来标识数据的顺序，数据必须按照顺序处理，如果前面的数据丢失，后面的数据就算到达了也不会通知应用层来处理。

另外 TLS 协议层面也有一个队头阻塞，因为 TLS 协议都是按照 record 来处理数据的，如果一个 record 中丢失了数据，也会导致整个 record 无法正确处理。

概括来讲，TCP 和 TLS1.2 之前的协议存在着结构性的问题，如果继续在现有的 TCP、TLS 协议之上实现一个全新的应用层协议，依赖于操作系统、中间设备还有用户的支持。部署成本非常高，阻力非常大。

所以 QUIC 协议选择了 UDP，因为 UDP 本身没有连接的概念，不需要三次握手，优化了连接建立的握手延迟，同时在应用程序层面实现了 TCP 的可靠性，TLS 的安全性和 HTTP2 的并发性，只需要用户端和服务端的应用程序支持 QUIC 协议，完全避开了操作系统和中间设备的限制。

QUIC 核心特性连接建立延时低

0RTT 建连可以说是 QUIC 相比 HTTP2 最大的性能优势。那什么是 0RTT 建连呢？这里面有两层含义。

传输层 0RTT 就能建立连接。
加密层 0RTT 就能建立加密连接


