**惰性删除**

1. 当读取一个已过期的键时，Redis 不会立即删除它，而是将它标记为过期，然后等待下次访问该键时再删除它。
2. Redis 对于每个数据库都会创建一个定时器（dict），每隔一段时间，Redis 会从定时器中随机选择一些过期键进行检查，如果发现某个键已过期，则将其删除。
