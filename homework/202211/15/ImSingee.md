软链接：记录的是指向的路径，可跨文件系统、可指向目录；被指向文件删除后原文件不可用
硬链接：记录的是指向的 inode，通常不可跨文件系统，仅支持文件；指向建立；链接建立后任一文件删除不会影响到原文件
