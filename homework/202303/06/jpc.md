# HTTP/1.0，HTTP/1.1，HTTP/2，HTTP/3的区别
## HTTP/1.0
无状态、无连接，有队头阻塞
## HTTP/1.1
1. 简单
HTTP 基本的报文格式就是 header + body，头部信息也是 key-value 简单文本的形式，易于理解

2. 灵活、易扩展
各类请求方法、URL、状态码，等每个组成都没有固定死，开发者可以自定义与扩充
HTTP在应用层其下层可以灵活变化（https就是HTTP与TCP之间增加SSL/TSL安全传输协议）

3. 应用广泛、支持跨平台

新增：
长连接、管道网络传输（但任然有队头阻塞）

## HTTP/2
头部压缩、二进制格式、并发传输、服务器主动推送

## HTTP/3
TCP改成UDP+QUIC
无队头阻塞、更快连接、连接迁移

