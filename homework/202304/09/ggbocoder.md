死锁是指在多进程并发执行时，由于竞争资源而导致的一种僵局状态，即两个或更多进程无限期地等待系统中的资源。

死锁的四个必要条件是：

- 互斥（Mutual exclusion）：至少有一个资源处于非共享模式下，即该资源只能同时被一个进程占用。
- 占有和等待（Hold and wait）：某个进程至少已经获取了一个资源，但又提出了新的资源需求，而该资源已被其他进程占有，则该进程会被阻塞，但它仍然持有已经获得的资源。
- 非剥夺（Non-preemptive）：资源不能被抢占，只能在进程完成使用后自动释放。
- 循环等待（Circular wait）：存在一个进程等待序列 P1、P2、……Pn，其中 P1 等待的资源被 P2 占用，P2 等待的资源被 P3 占用……Pn 等待的资源被 P1 占用。这样就形成了一个进程循环等待环路。