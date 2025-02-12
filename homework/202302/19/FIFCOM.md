## Redis的优势和劣势是什么？

优点：
1. 数据存储在内存， 读写速度快，性能优异
2. 支持数据持久化，便于数据备份、恢复
3. 支持简单的事务，操作满足原子性
4. 支持String、List、Hash、Set、Zset五种数据类型，满足多场景需求
5. 支持主从复制，实现读写分离，分担读的压力
6. 支持哨兵机制，实现自动故障转移

缺点：
1. 数据存储在内存，主机断电则数据丢失
2. 存储容量受到物理内存的限制，只能用于小数据量的高性能操作
3. 在线扩容比较困难，系统上线时必须确保有足够的空间
4. 用于缓存时，易出现缓存雪崩，缓存击穿等问题