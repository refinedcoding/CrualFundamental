### What is starvation and aging in OS?

饥饿：饥饿是一种资源管理问题，其中一个进程由于资源被分配给其他进程而长时间得不到所需的资源。

老化：老化是一种在调度系统中避免饥饿的技术。 它通过向每个请求的优先级添加老化因素来工作。 老化因子必须随着时间的推移增加请求的优先级，并且必须确保请求最终成为最高优先级的请求（在它等待足够长的时间之后）
