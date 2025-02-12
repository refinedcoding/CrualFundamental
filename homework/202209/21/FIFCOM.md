## 在操作系统中，什么是饥饿和老化

饥饿或无限期阻塞是一种与优先级调度算法有关的现象，在这种情况下，一个准备获得CPU（资源）的进程可以因为低优先级而无限期地等待运行。在一个高负荷的计算机系统中，源源不断的高优先级进程可以阻止低优先级的进程获得CPU。

饥饿的解决方案：老化

老化是一种逐步提高在系统中等待了很长时间的进程的优先级的技术。例如，如果优先级范围从127（低）到0（高），我们可以每15分钟增加一个等待进程的优先级1。最终，即使是一个初始优先级为127的进程，也需要不超过32个小时的时间，使优先级为127的进程老化为优先级为0的进程。