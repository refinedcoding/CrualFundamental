堆排序原理：堆是一个完全二叉树，可以用数组表示，满足堆中某个结点的值总是不大于或不小于其父结点的值。这样堆的根节点就一定是最小值或者最大值。

我们每一次取出根节点的值，把末尾值填充进去，然后再维护一次堆，即可不断取出最小值，从而完成排序。



归并排序原理：把两个有序数组合并成一个，可以$O(n)$完成，从而我们可以分治，把数组分成两部分之后，再分别把左和右变成有序，再合并，从而
$$
T(n)=2*T(\frac n2)+O(n)
$$
稳定排序：

假设元素为$(成绩，姓名)$ 

原数据为： (1,小明) (2,小李) (1,小王) 

若能保持按照成绩排序之后，小明仍然在小王前面，则为稳定排序。

假定在待排序的记录序列中，存在多个具有相同的关键字的记录，若经过排序，这些记录的相对次序保持不变，即在原序列中，r[i]=r[j]，且r[i]在r[j]之前，而在排序后的序列中，r[i]仍在r[j]之前，则称这种排序算法是稳定的

*稳定排序包括插入排序、冒泡排序、归并排序、基数排序*

*非稳定排序算法包括：选择排序、快速排序、希尔排序、堆排序*

