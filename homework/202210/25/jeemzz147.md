### git中merge和rebase区别


Merge命令会保留所有commit的历史时间。每个人对代码的提交是各式各样的。尽管这些时间对于程序本身并没有任何意义。但是merge的命令初衷就是为了保留这些时间不被修改。这样也就形成了以merge时间为基准的网状历史结构。每个分支上都会继续保留各自的代码记录, 主分支上只保留merge的历史记录。子分支随时都有可能被删除。


merge操作会生成一个新的节点，之前提交分开显示。而rebase操作不会生成新的节点，是将两个分支融合成一个线性的操作。

通过上面可以看到，想要更好的提交树，使用rebase操作会更好一点，这样可以线性的看到每一次提交，并且没有增加提交节点。
