## 什么是Raft算法？

Raft 算法基于 Multi-Paxos 算法进行重新简化设计和实现，提高了工程实践性。Raft 算法的主要设计思想与 ZAB 类似，通过先选出领导节点来简化流程和提高效率。实现上解耦了领导者选举、日志复制和安全方面的需求，并通过约束减少了不确定性的状态空间。

算法包括三种角色：领导者（Leader）、候选者（Candidate） 和跟随者（Follower），每个任期内选举一个全局的领导者。领导者角色十分关键，决定日志（log）的提交。每个日志都会路由到领导者，并且只能由领导者向跟随者单向复制。
典型的过程包括两个主要阶段：

领导者选举：开始所有节点都是跟随者，在随机超时发生后未收到来自领导者或候选者消息，则转变角色为候选者（中间状态），提出选举请求。最近选举阶段（Term）中得票超过一半者被选为领导者；如果未选出，随机超时后进入新的阶段重试。领导者负责从客户端接收请求，并分发到其他节点；

同步日志：领导者会决定系统中最新的日志记录，并强制所有的跟随者来刷新到这个记录，数据的同步是单向的，确保所有节点看到的视图一致。

此外，领导者会定期向所有跟随者发送心跳消息，跟随者如果发现心跳消息超时未收到，则可以认为领导者已经下线，尝试发起新的选举过程。
