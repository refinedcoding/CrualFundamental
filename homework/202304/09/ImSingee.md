死锁：两个资源相互依赖，互为其前置条件
产生死锁的四个必要条件
互斥条件：一个资源每次只能被一个进程使用。
请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放。
不剥夺条件：进程已获得的资源，在末使用完之前，不能强行剥夺。
循环等待条件：若干进程之间形成一种头尾相接的循环等待资源关系。
