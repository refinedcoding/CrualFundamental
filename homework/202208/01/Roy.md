### 什么是死锁（Deadlock）、饥饿（Starvation）和活锁（Livelock）
#### 死锁
1. 互斥条件（mutual exclusion）：临界资源是独占资源，进程应互斥且排他地使用这些资源。
2. 占有和等待条件（hold and wait）:进程在请求资源得不到满足而等待时，不释放已占有资源。
3. 不剥夺条件（no preemption）:又称不可抢占，已获资源只能由进程自愿释放，不允许被其他进程剥夺。
4. 循环等待（circular wait）：又称环路条件，存在循环等待链，其中，每个进程都在等待链中等待下一个进程所持有的资源，造成这组进程处于永远等待状态。

#### 活锁
> 当线程正在等待永远不会变得可用的资源，而CPU忙于释放和获取共享资源时，就会发生Livelock。 它与死锁类似，不同之处在于，活锁中涉及的进程状态不断变化，并且频繁执行而没有取得进展。
#### 饥饿
> 当线程（未死锁）在队列中等待不可接受的长时间以获取用于访问共享资源的锁时，就会发生挂起。
