- [[聚簇索引]]  
	- 用于找到最终数据（与非聚簇索引比较）  
	- MySQL 默认主键就是聚簇索引；如果没有主键则使用唯一索引；如果还没有则自动生成一个  
	- 通常使用 [[B+ 树]] 以支持范围查找  
- [[哈希索引]]  
	- 仅适用于精确查询，不支持范围查询  
