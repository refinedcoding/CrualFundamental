## Redis 如何实现延迟队列？
在redis中zset可以实现延迟队列，zset中有一个score属性可以用来存储延迟执行时间。
使用zadd score1 value1可以往内存中生产消息，zrangebysorce查询符合条件的所有待处理的任务，通过循环执行队列即可