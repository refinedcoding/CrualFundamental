命名管道：
- 在同一台计算机的不同进程之间，支持可靠的，单向或者双向的数据通信

消息队列： 
- 消息队列少了打开和关闭管道的复杂，提供了一种从一个进程向另一个进程发送数据块的方法
- 每个数据块被认为含有一个类型，接受进程可以独立地接收含有不同类型值的数据块

