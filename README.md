# c++学习笔记

自我复习记录，大多数参考[代码随想录](https://github.com/youngyangyang04/leetcode-master/blob/master/README.md)

[Git操作](./basics/Git操作.md)

[linux常用操作](./basics/linux常用操作.md)

[#include <cmath>](./basics/cmath.md)

[ns3命令](./basics/ns3命令.md)

## 简单数据结构

1. [数组](./basics/数组.md)
2. [string](./basics/string.md)
3. [顺序容器（vector,deque）](./basics/顺序容器（vector,deque）.md)
4. [顺序容器适配器（stack,queue,priority_queue）](./basics/顺序容器适配器（stack,queue,priority_queue）.md)



## 链表



## Hash表

1. [hash表基础知识](./basics/hash表基础知识.md)
2. 



## 二叉树

### 二叉树基础题

1. [二叉树基础知识](./basics/二叉树.md)
2. [二叉树的递归遍历-前中后序遍历](./problems/144.94.145.二叉树的前中后序遍历.md)
3. [二叉树的层序遍历](./problems/102.二叉树的层序遍历.md)
4. [翻转二叉树-简单](./problems/226.翻转二叉树-简单.md)
5. [对称二叉树-简单](./problems/101.对称二叉树-简单.md)
6. [二叉树的最大深度-简单](./problems/104.二叉树的最大深度-简单.md)
7. [二叉树的最小深度-简单](./problems/111.二叉树的最小深度-简单.md)
8. [完全二叉树的节点个数-简单](./problems/222.完全二叉树的节点个数-简单.md)
9. [平衡二叉树-简单](./problems/110.平衡二叉树-简单.md)



## 算法

1. [算法复杂度](./basics/算法复杂度.md)
2. 



## 贪心算法 

1. [贪心算法理论基础](./basics/贪心算法理论基础.md)
2. [分发饼干-简单](./problems/455.分发饼干-简单.md)
3. [摆动序列-中等](./problems/376.摆动序列-中等.md)
4. [最大子数组和-中等（走进死胡同过半天没做出来）](./problems/53.最大子数组和-中等.md)
5. [跳跃游戏-中等](./problems/55.跳跃游戏-中等.md)
6. [跳跃游戏II-中等](./problems/45.跳跃游戏II-中等.md)



## 动态规划

1. [动态规划理论基础](./basics/动态规划理论基础.md)
2. [不同的二叉搜索树-困难](./problems/96.不同的二叉搜索树-困难.md)
3. [整数拆分-中等](./problems/343.整数拆分-中等.md)







## 图论

### DFS - 递归

DFS（深度优先搜索） 常用来解决可达性的问题。

标记：和 BFS 一样同样需要对已经遍历过的节点进行标记。

### 无向图的连通分量问题

1. [岛屿数量-中等](./problems/200.岛屿数量-中等.md)
2. [岛屿的最大面积-中等](./problems/695.岛屿的最大面积-中等.md)

### BFS

BFS（广度优先搜索） 常用来解决最短路径问题。第一次遍历到目的节点时，所经过的路径是最短路径。只能用来求解**无权图**的最短路径问题

队列：用来存储每一层遍历得到的节点
标记：对于遍历过的结点，应将其标记，以防重复访问

1. [获取你好友已观看的视频-中等](./problems/1311.获取你好友已观看的视频-中等.md)

### Dijstra

1. [细分图中的可到达结点-困难(没做出来看的题解)](./problem/882.细分图中的可到达结点-困难.md)



### 并查集（环问题）

[冗余连接-中等](./problems/684.冗余连接-中等.md)
