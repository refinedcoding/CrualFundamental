### 什么是基数树(Radix Trie)？


基数树（Radix Trie，也叫基数特里树或压缩前缀树），是一种更节省空间的Trie（前缀树），其中作为唯一子节点的每个节点都与其父节点合并，边既可以表示为元素序列又可以表示为单个元素。 因此每个内部节点的子节点数最多为基数树的基数r ，其中r为正整数，x为2的幂，x≥1，这使得基数树更适用于对于较小的集合（尤其是字符串很长的情况下）和有很长相同前缀的字符串集合。
