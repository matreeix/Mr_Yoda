# 前言

​		众所周知，“程序 = 数据结构 + 算法”，本项目旨在总结常用又经典的数据结构和算法实现，可以作为生活工作学习的参考:)

# **数据结构**

- ## **线性结构**

  - 数组

    - 动态数组

  - 链表

    - 单向链表的底层实现

    - 特殊操作

      > 单向链表的翻转、排序、合并、树形转化

    - 单向链表相交

    - 含环的单向链表（约瑟夫问题）

    - 跳表

      > 跳表是一个随机化的数据结构，一种可以进行二分查找的有序链表。

    - 双向链表

  - 栈 

    > 栈是先进后出的数据结构

    - 单调栈
    - 数组实现栈
    - 链表实现栈
    - 队列实现栈
    - 栈实现计算器功能

  - 队列

    > 队列是先进先出的数据结构

    - 单调队列
    - 数组实现队列
    - 链表实现队列
    - 栈实现队列
    - 循环队列
    - 优先队列(堆)

- ## **树型结构**

  - 二叉树

    - 基础

      > 二叉搜索树、完全二叉树、满二叉树

    - 自平衡二叉查找树

      > AVL树、红黑树([AVL树和红黑树的性能比较](https://zhuanlan.zhihu.com/p/93369069))

    - 最优二叉树（huffman树）

    - 堆

      > BFPRT算法（TOP-K问题）、大根堆、小根堆

    - 二叉索引树（树状数组或Fenwick树）

    - 二叉树的遍历（前序、中序、后序、层序、morris）

    - 二叉树的序列化和反序化

  - 多叉树

    - 线段树

    - B树类

      > B树、B+树、B-树、2-3树

    - Trie（字典树）

      > 前缀树、后缀树、基数树

    - UF（并查集）

    - 多叉树的遍历

- ## **图结构**

  - 邻接表
  - 邻接矩阵

# **算法**

- ## 算法复杂度

  - 空间复杂度

    > 状态压缩

  - 时间复杂度

    > 一般ACM或者笔试题的时间限制是1秒或2秒。在这种情况下，C++代码中的操作次数控制在 10^7∼10^8 为最佳。
    >
    > 下面给出在不同数据范围下，代码的时间复杂度和算法该如何选择：
    >
    > 1. n≤30, 指数级别, dfs+剪枝，状态压缩dp；
    > 2. n≤100 => O(n^3)，floyd，dp，高斯消元；
    > 3. n≤1000 => O(n^2)，O(n^2*logn)，dp，二分，朴素版Dijkstra、朴素版Prim、Bellman-Ford；
    > 4. n≤10000 => O(n^(3/2))，块状链表、分块、莫队；
    > 5. n≤100000 => O(nlogn) => 各种sort，线段树、树状数组、set/map、heap、拓扑排序、dijkstra+heap、prim+heap、spfa、求凸包、求半平面交、二分、CDQ分治、整体二分；
    > 6. n≤1000000 => O(n), 以及常数较小的 O(nlogn)算法 => 单调队列、 hash、双指针扫描、并查集、kmp、AC自动机，常数比较小的 O(nlogn) 的做法：sort、树状数组、heap、dijkstra、spfa；
    > 7. n≤10000000 => O(n)，双指针扫描、kmp、AC自动机、线性筛素数；
    > 8. n≤10^9 => O(n^(1/2))，判断质数；
    > 9. n≤10^18 => O(logn)，最大公约数，快速幂；
    > 10. n≤10^1000 => O((logn)^2)，高精度加减乘除；
    > 11. n≤10^100000 => O(logk*loglogk)，k表示位数，高精度加减、FFT/NTT；
    >
    > 作者：yxc
    > 链接：https://www.acwing.com/blog/content/32/

- ## 基本思想

  - 贪心

    > 贪心算法（又称贪婪算法）是指，在对问题求解时，总是做出在当前看来是最好的选择。也就是说，不从整体最优上加以考虑，他所做出的是在某种意义上的局部最优解。
    >
    > 贪心算法不是对所有问题都能得到整体最优解，关键是贪心策略的选择，选择的贪心策略必须具备**无后效性**，即某个状态以前的过程不会影响以后的状态，只与当前状态有关。

  - 回溯

    > 回溯算法实际上一个类似枚举的搜索尝试过程，主要是在搜索尝试过程中寻找问题的解，当发现已不满足求解条件时，就 “回溯” 返回，尝试别的路径。回溯法是一种选优搜索法，按选优条件向前搜索，以达到目标。但当探索到某一步时，发现原先选择并不优或达不到目标，就退回一步重新选择，这种走不通就退回再走的技术为回溯法，而满足回溯条件的某个状态的点称为 “**回溯点**”。许多复杂的，规模较大的问题都可以使用回溯法，有“通用解题方法”的美称。

  - 分治

    > 在计算机科学中，分治法是构建基于多项分支递归的一种很重要的算法范式。字面上的解释是「**分而治之**」，就是把一个复杂的问题分成两个或更多的相同或相似的子问题，直到最后子问题可以简单的直接求解，原问题的解即子问题的解的合并。

  - 枚举

    > 枚举算法就是我们通常使用的**暴力解法**，它的核心思想就是:枚举所有的可能。
    >
    > 枚举法的本质就是从所有候选答案中去搜索正确的解,使用该算法需要满足两个条件：(1)可预先确定候选答案的数量；(2)候选答案的范围在求解之前必须有一个确定的集合。

- ## **排序**

  - 经典排序算法：

    - 冒泡排序

    - 选择排序

    - 插入排序

      > 前三种排序的平均时间复杂度较大，一般针对随机的大量的数据排序时不会使用到，但数据量较小时，或者数据有序性较高时，他们的性能并不一定比快排差，甚至能优于快排；所以这三种排序的算法思想是一定要掌握的，有些算法问题就是它们的变体应用，使用了甚至有奇效:)

    - 希尔排序（逆序对）

    - 归并排序（自底向上、自顶向下）

    - 快速排序（随机快排、双路快排、三路快排）

    - 桶排序

    - 基数排序

    - 计数排序

    - 堆排序

      > 排序算法的总结如下

    ![1231](https://mmbiz.qpic.cn/mmbiz_png/QCu849YTaIOOdfiakqsTRHKk9icjqQZJYuUQSibiaZIayLeW08icZul2EH9VqMgbeMN3nhfic7Wxfb8Ctk4Oicwj6DQ0Q/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

  - 其他排序算法：

    - 拓扑排序

      > 对一个有向无环图(Directed Acyclic Graph，简称DAG)G进行拓扑排序，即是将G中所有顶点排成一个线性序列，使得图中任意一对顶点u和v，若边<u,v>∈E(G)，则u在线性序列中出现在v之前。通常，这样的线性序列称为满足拓扑次序(Topological Order)的序列，简称拓扑序列。简单的说，由某个集合上的一个偏序得到该集合上的一个全序，这个操作称之为拓扑排序。

- ## **查找**

  - 二分查找

    > 一维二分查找、二维二分查找

  - 斐波那契查找

    > 斐波那契搜索(Fibonacci search) ，又称斐波那契查找，是有限区间中单峰函数的搜索技术，是在二分查找的基础上根据[斐波那契数列](https://baike.baidu.com/item/斐波那契数列/99145)进行分割的。在斐波那契数列找一个等于或略大于查找表中元素个数的数F[n]，将原查找表扩展为长度为F[n]（如果要补充元素，则补充重复最后一个元素，直到满足F[n]个元素），完成后进行斐波那契分割，即F[n]个元素分割为前半部分F[n-1]个元素，后半部分F[n-2]个元素，找出要查找的元素所在那一部分进行递归，直到找到。
    >
    > 已经证明，斐波那契搜索是一种函数估值次数最少的最优搜索方法。

  - 插值查找

    > 插值查找是根据查找关键字与查找表中最大最小记录关键字比较后的查找方法。插值查找基于二分查找，将查找点的选择改进为自适应选择，提高查找效率，适合于关键字值分布均匀的集合。

- ## 数学原理

  - 数论

    - 快速幂算法

      > 顾名思义，快速幂就是快速算底数的n次幂。其时间复杂度为 O(log₂N)， 与朴素的O(N)相比效率有了极大的提高。

    - 欧几里得算法

      > 欧几里德算法又称辗转相除法，是指用于计算两个非负整数a，b的最大公约数。计算公式gcd(a,b) = gcd(b,a mod b)。

    - 欧拉函数

      > 对正整数n，欧拉函数是小于或等于n的正整数中与n互质的数的数目（φ(1)=1）。
    - 同余定理
    
      > 给定一个正整数 m，如果两个整数 a 和 b 满足 a - b 能够被 m 整除，即(a-b)/m得到一个整数，那么就称整数 a 与 b 对模 m 同余，记作 a ≡ b(mod m)。
      >
      > (a+b)%m = (a%m+b%m)%m;
      >
      > a**b%m = ((a%m)*(b%m))%m;
      >
      > 注：同余只对“+”、“×”成立，对“-”、“/”不成立
    
    - 素数判断

      > 试除法、朴素筛法、线性筛法

  - 排列组合

    > 杨辉三角、求组合数、卡特兰数

  - 矩阵

    > 高斯消元法、矩阵快速幂

  - 几何

    - 海伦公式

      > $$
      > S=\sqrt{p(p-a)(p-b)(p-c)}
      > $$
      >
      > 其中，a、b、c为三角形三边长，p为半周长。

    - 鞋带公式

      > Shoelace公式，也叫高斯面积公式，是一种数学算法，可求确定区域的一个简单多边形的面积。该多边形是由它们顶点**描述笛卡尔坐标中的平面**。用户**交叉相乘**相应的坐标以找到包围该多边形的区域，并从周围的多边形中减去该区域以找到其中的多边形的区域。之所以称为鞋带公式，是因为对构成多边形的坐标进行恒定的交叉乘积，就像系鞋带一样。
      >
      > ——以上来自维基百科。
      > $$
      > A = \frac{1}{2} |\sum_{i=1}^{n}{x_i(y_{i+1}-y_{i-1})}|=\frac{1}{2} |\sum_{i=1}^{n}{y_i(x_{i+1}-x_{i-1})}|=\frac{1}{2} |\sum_{i=1}^{n}\begin{pmatrix}
      > x_i & x_{i+1}\\
      > y_i & y_{i+1}
      > \end{pmatrix}|
      > $$

  - 概率

    - Knuth洗牌算法

    - 蒙特卡洛算法计算PI

      > 蒙特卡洛算法是以概率和统计的理论、方法为基础的一种计算方法，将所求解的问题同一定的概率模型相联系；用电子计算机实现统计模拟和抽样，以获得问题的近似解，故又称统计模拟法或统计实验法。

    - 拒绝采样

      > 拒绝采样基于以下观察：在一维中对随机变量进行采样，可以对二维笛卡尔图执行均匀随机采样，并将样本保持在其密度函数图下的区域中。

- ## 计算机原理

  - 递归

    > 汉诺塔问题

  - 位运算

    > 汉明重量、幂集、格雷编码、N皇后的优化

- ## **字符串算法**

  - KMP算法

    > 字符串匹配算法

  - Manacher算法

    > 查找一个字符串的最长回文子串的线性算法
  - 后缀数组(占坑)
  
    > 在计算机科学里, **后缀数组**（英语：suffix array）是一个通过对字符串的所有后缀经过排序后得到的数组。此数据结构被运用于全文索引、数据压缩算法、以及生物信息学。后缀数组被乌迪·曼伯尔与尤金·迈尔斯于1990年提出，作为对[后缀树](https://baike.baidu.com/item/后缀树)的一种替代，更简单以及节省空间。它们也被Gaston Gonnet 于1987年独立发现，并命名为“PAT数组”。——百度百科
    >
    > 参考文献：《后缀数组——处理字符串的有力工具》                

- ## **哈希算法**

  - 布隆过滤器

    > 输入数据个数为n，误判率p，哈希函数个数k，布隆过滤器容量m
    > $$
    > m = - \frac{nlnp}{(ln2)^2}
    > $$
    >
    > $$
    > k = \frac{m}{n}ln2
    > $$
    >
    
- 一致性哈希
  - 滚动哈希(Rabin-Karp算法)
  
- 哈希碰撞
  
  - Rehash法
    - 链地址法
  
- ## **图算法**

  - 图的表示

  - 深度优先遍历

    > 单源路径、连通分量、无向图环检测、二分图检测、桥和割点

  - 广度优先遍历

    > 无权图最短路径、多源BFS、BFS和DFS联系、floodfill算法

  - 哈密尔顿路径和欧拉路径

    > Hierholzer 算法

  - 最小生成树

    > 切分定理、Kruskal 算法、Prim算法

  - 最短路径算法

    > Dijkstra 算法、 Bellman-Ford 算法、Floyd 算法、A*算法

  - 有向图

    > 拓扑排序、Kosaraju 算法

  - 网络流

    > Ford-Fulkerson 思想、Edmonds-Karp 算法

  - 匹配问题

    > 二分图匹配算法、匈牙利算法

- ## **动态规划**

  - 背包问题

    > 01背包、完全背包、多重背包、混合背包、二维背包、分组背包、求方案数背包、求具体方案背包、有依赖的背包

  - 线性DP

    > LIS、LCS、编辑距离、股票买卖系列（有限状态机）、最大子序和

  - 区间DP

    > 最长回文子序列

  - 树形DP

    > 鸡蛋掉落

  - 状态压缩DP

    > 骑士拨号器

  - 数位DP

    > 统计1的个数

  - 博弈型DP

    > 翻转游戏、Nim游戏、石子游戏、井字游戏

    - 策梅洛定理

      > **策梅洛定理**是[博弈论](https://wiki.mbalib.com/wiki/博弈论)的一条定理，以恩斯特·策梅洛命名。定理表示在二人的有限游戏中，如果双方皆拥有完全的资讯，并且运气因素并不牵涉在游戏中，那先行或后行者当中必有一方有必胜/必不败的策略。若运用至国际象棋，则策梅洛定理表示“要么黑方有必胜之策略、要么白方有必胜之策略、要么双方也有必不败之策略”。

- ## 多线程算法

  - 多线程归并排序

- ## 智能算法(占坑)

  - 蚁群算法

  - 遗传算法

  - 粒子群算法

  - 模拟退火算法

  - 禁忌搜索算法

  - 应用

    > TSP问题(旅行商问题)

- ## 算法设计

  - 缓存设计

    > LFU、LRU

  - 雪花算法

    > 生成分布式系统全局唯一ID

  - 设计推特

  - 神奇的指针

    - 双指针

      > 快慢指针、左右指针

    - 多指针

- ## 算法可视化

  - 迷宫生成

    > BFS、DFS、随机队列

  - 排序可视化

  - 扫雷游戏

    > Knuth洗牌算法

  - 概率模拟

    > 蒙特卡洛算法、三门问题

  - 分形绘制

    > 计算几何、树形、雪花形