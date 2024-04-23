# 算法与数据结构-以Java为例（梅努斯大学）

## 什么是计算机程序

定义：一个计算机程序=数据结构+算法

A Computer Program = Data structures + Algorithms

计算机程序本质上就是一堆机器码构成的指令集，cpu通过读取指令来执行任务。

数据结构决定了cpu在生成数据后，保存在内存的数据以何种方式存储

算法决定了cpu以何种方式或顺序运行指令

## 数据结构

数据结构数据结构是一种存储和组织数据以方便访问的方法和修改。

A data structure is a way to store and organise data in order to facilitate access and modifications.

没有一种数据结构适用于所有目的，因此重要的是了解其中几种方法的优点和局限性。

 No single data structure works well for all purposes, and so it is important to know the strengths and limitations of several of them.

### 一些基础的数据类型

Queues 队列

 Stacks 栈

 Linked Lists 链表

Trees  树

Graphs  图表

Hash Tables 哈希表

## 算法

非正式地说，算法是任何定义良好的计算过程，它以一些值或一组值作为输入，并产生一些值或一组值作为输出。

它是一种解决特定计算问题的工具。

### 算法的特征

- 带有一定输入
- 获得一定输出
- 它是一种cpu执行的计算过程

### 算法的正确性

如果一个算法对于每个输入实例，都以正确的输出停止，那么它就是正确的。

An algorithm is said to be correct if, for every input instance, it halts with the correct output. We say that a correct algorithm solves the given computational problem.

我们说一个正确的算法可以解决给定的计算问题。一个不正确的算法在某些输入实例上可能根本不会停止，或者它可能会因为一个不正确的答案而停止。不正确的算法有时是有用的，如果我们能控制它们的错误率(找到大素数)。

 An incorrect algorithm might not halt at all on some input instances, or it might halt with an incorrect answer. Incorrect algorithms can sometimes be useful, if we can control their error rate (finding large prime numbers). 

通常，我们只关心正确的算法。

Ordinarily, we shall be concerned only with correct algorithms.

### 对算法的分析

分析一种算法意味着预测该算法所需的资源。偶尔，诸如内存、通信带宽或计算机硬件之类的资源是主要关注的，但最常见的是我们想度量的计算时间。

Analysing an algorithm has come to mean predicting the resources that the algorithm requires. Occasionally, resources such as memory, communication bandwidth, or computer hardware are of primary concern, but most often it is computationaltime that we want to measure

### 算法的重要性

我们分析算法，目的就是为了计算出哪种算法能够调用更少的资源、花费更少的计算和运行时间，这就是我们需要考虑算法的重要性

好的算法能够节省内存空间，让cpu能更好地高效工作

对比以下两种算法：

**线性搜索**和**二分法搜索**

![img](https://upload-images.jianshu.io/upload_images/28917406-7a10896ccd2b6a23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

二分搜索比线性搜索快32,000,000倍!

### 输入大小和运行时间

#### 输入大小

输入大小的最佳概念取决于所研究的问题。对于许多问题，例如排序或计算离散傅里叶变换，最常见的度量是输入项的数量。例如，数组大小n用于排序。

The best notion for input size depends on the problem being studied. For many problems, such as a sorting or computing discrete Fourier transforms, the most common measure is the number of items in the input. For example, the array size 𝑛𝑛 for sorting.

**总的来说，输入大小是算法为解决实际问题预设的一个输入大小或问题的容量（尺寸）**

比如要对一个数组进行排序，那么输入大小就是数组的长度

#### 运行时间

算法在特定输入上的运行时间是执行的基本操作或“步骤”的数量。定义步长的概念使其尽可能地与机器无关是很方便的。

所以运行时间的定义为，**在不同的平台上执行某个算法到结束所需的执行次数或步长，它通常和n有联系，是n的函数，也有可能没有关系**，单位为1

The running time of an algorithm on a particular input is the number of primitive operations or “steps” executed. It is convenient to define the notion of step so that it is as machine-independent as possible.

在某个具体的平台上时，它又被定义为基础单位时间（因平台而异）*步长（不同平台统一的运行时间），单位是时间相关的单位（秒，微妙，纳秒等）

### 最坏情况、平均情况和最佳情况

我们通常只专注于寻找最坏情况的运行时间，也就是说，**对于任何大小为n的输入，最长的运行时间**。例如，在线性搜索中，当搜索项不在数组中时。

最坏情况为我们提供了任何输入的运行时间的上限。知道它保证了算法永远不会花费更长的时间。对于一些算法，最坏的情况经常发生。

平均情况通常与最坏情况大致相同。最好的情况很少发生，所以我们对此不感兴趣。例如，在线性搜索，搜索项应该位于数组的开头。

三种情况的出现由问题的输入情景决定

一般我们研究的研究时间，通常是以**最坏情况**来计算的

举例：以线性搜索和二分法搜索为例，三种情况分别如下：

![img](https://upload-images.jianshu.io/upload_images/28917406-76784439dbabc8df.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 增长速率（Order of growth）

我们现在做一个更简单的抽象:我们真正感兴趣的是运行时间的增长速度或增长顺序。

We now make one more simplifying abstraction: it is the rate of growth, or order of growth, of the running time that really interests us

增长速率的定义为：单位n的变化下对应运行时间的变化，即d（运行时间)/d(n),也是运行时间关于n的微分

我们只考虑公式的前项，因为对于较大的n值，低阶项相对不重要。例如，如果一个算法的增长速度是50 + 3x + 100x^2，我们只考虑100x^2项。

我们也忽略了前项的常数系数，因为在决定大输入的计算效率方面，常数因素不如增长率重要。

因此，我们从100x^2项中选择x^2项。

对于线性搜索，我们使用O(n)(发音为“theta of n”)来表示它的运行时间。

#### 为什么常数和低阶项不重要？

对一个算法来说，我们要研究的是它随输入的变化趋势，在巨量样本的背景下，低阶项的存在对运行时间的变化趋势影响不大，常数项甚至除了数值大小以外对增长率毫无影响

#### 领先项（leading term)

领先项：对变化起决定作用的、阶数最大的单项式

因此，在实际分析算法时，我们只研究它的领先项，同时，这个领先项不必带有任何常数

结合以下图，有助于理解的更加深刻：

![img](https://upload-images.jianshu.io/upload_images/28917406-9c06cd9fdcef8922.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以确定，当输入数(n)变大时，这些项：100 + x, 10x, x^2,x^4,2^x与这一项100(2^x)有显著差异。

此外，通过比较f(x) = x、f(x) = 100 + x和f(x) = 10x的图，我们可以看到常数数(100和10)并没有改变增长率的模式。

类似地，通过比较off(x) = x2与f(x) = 100 x2的图也可以得到相同的结论。

这下能理解了吧？

#### 内存问题（Memory problem）

一些算法所需要的内存数量可能会导致内存问题。

让我们看看计算斐波那契数列第n项的两种算法。

1)非递归

```java
long Fibo_NonRecursive(int n)
{
n1 = 0;
n2 = 1;
if( n == 0)
return n1;
for (i = 2; i <= n; i++)
{
sum = n1 + n2;
n1 = n2;
n2 = sum;
}
return n2;
}
```

2)递归

```java
long Fibo_Recursive(long n)
{
if (n <= 1)
return n;
return Fibo_Recursive(n-1) + Fibo_Recursive(n-2);
}
```

可以看出，当查找索引大于40时，递归算法需要大量的时间。

此外，对于较大的输入，可能会发生堆栈溢出。

堆栈是计算机系统使用的内存之一。

因此，我们已经看到内存是一些算法的问题之一。

## 算法基础

### 插入算法(Insertion Sort)

输入:n个数字的序列a1, a2，…,an。

输出:将a1按照升序形式排列

我们希望排序的数字也称为键值

- 插入排序是一种对少量元素进行排序的有效算法。
- 插入排序的工作方式就像对一手牌进行排序。
- 我们从左手空着手，牌面朝下放在桌上。然后，我们每次从桌子上取出一张牌，并将其插入左手的正确位置。为了找到一张牌的正确位置，我们从右到左将它与手中已有的每张牌进行比较。
- 在任何时候，左手拿着的牌都是排序的，这些牌本来是桌子上一堆牌中最上面的。

#### 图示

![img](https://upload-images.jianshu.io/upload_images/28917406-df40ea3d1ce00328.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<div style="text-align:center">如图所示</div>

#### 关键代码

![img](https://upload-images.jianshu.io/upload_images/28917406-fdbacef7f48f3ddd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 思路

索引i表示插入手牌的“当前牌”。

在以i为索引的“outer”for循环的每次迭代开始时，由元素A[1..i-1]构成当前排序的手，元素A[i +1..n]对应于仍在桌子上的那堆纸牌。

事实上，元素A[1..i -1]是最初位于位置1到i -1的元素，但现在按顺序排列。我们称这些元素为循环不变量（loop invariant），即历经循环后保持不变的量

我们陈述了A[1..i-1]形式为循环不变式:在第1-8行for循环的每次迭代开始时，子数组A[1..i .- 1]由原在A[1..i-1]但按顺序排列的数组。

#### 过程

1. 从index开始循环，表示为要被排序的数
2. 同时在循环内部框体再定义一个嵌套循环，从index前的数开始一张张与index所代表的数比大小
3. 若比较的数比index大，则在数组中向右移动一位
4. 若比较中出现比index小的数，则将index数放入该数字的位置，停止内循环
5. index加一，索引右移一位，以此类推，直到排序结束

## 数据结构基础

### **哈希表**（Hash Table）

### 二叉树（Binary Search Trees）

#### 定义

二叉树是支持许多动态集操作的数据结构，包括search、MINIMUM、MAXIMUM、PREDECESSOR、SUCCESSOR、INSERT和DELETE。

因此，我们既可以将搜索树用作字典，也可以将其用作优先队列。

二叉搜索树的基本操作所需的时间与树的高度成正比。对于一个有n个节点的完全二叉树，这样的操作在最坏情况下需要O(lgn)的时间。然而，如果树是一个有n个节点的线性链，同样的操作需要Θ(n)最坏情况时间。

The search trees are data structures that supports many dynamic-set operations, including SEARCH, MINIMUM, MAXIMUM, PREDECESSOR, SUCCESSOR, INSERT, and DELETE. Thus,we can usea searchtree both as a dictionaryand as a prior queue. Basic operations on a binary search tree take time proportional to the height of the tree. For a complete binary tree with 𝑛 nodes,such operations run in Θ(lg𝑛) worst case time. If the tree is a linear chain of n nodes, however, the same operations take Θ(𝑛) worst-case time.

二叉搜索树，顾名思义，是以二叉树的形式组织的。

#### 基本组成

我们用一个链接的数据结构来表示这样的树，其中每个节点都是一个对象。

此外，它主要包括一个键（key）和数据(value)，每个节点包含属性left（左子树）、right（右子树）和p（父子树），它们分别指向与其左子节点、右子节点和父节点相对应的节点。

如果缺少子元素或父元素，则相应的属性包含值NIL。根节点是树中父节点为NIL的唯一节点。树本身有一个指向根节点的属性根，如果树为空，则为NIL。根节点*T.root*是树T中父节点为NIL的唯一节点。

二叉搜索树对于任意节点x, x的左子树中的键值最多为x.key, x的右子树中的键值至少为x.key。不同的二叉搜索树可以表示相同的一组值。对于大多数搜索树操作来说，最坏情况下的运行时间与树的高度成正比。

```
数据储存方式：
基本单位：节点（object）
节点基本属性：
key(int...)
value(int...)
left(object)
right(object)
p(object)
```

![img](https://upload-images.jianshu.io/upload_images/28077103-a053b8e975d34149.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<div style="text-align:center">（根的键为5，其左子树中的键2、3和5不大于5，其右子树中的键7和8不小于5。该属性适用于树中的每个节点。例如，例1中的键3不小于左子树中的键2，也不大于右子树中的键5）</div>

#### 性质

- **二叉搜索树中的键总是以满足二叉搜索树属性的方式存储**

  设x是二叉搜索树中的一个节点。如果y是x的左子树中的一个节点，则y.key≤x.key。

  如果y是x右子树中的一个节点，则y.key>=x. key

  也就是说，一个节点的左子树下派生的节点对应的键始终比该节点对应存储的键要小

  右子树下派生的节点对应的键始终比该节点对应存储的键要大

#### 有序树径（InorderTree Walk）

由于二叉搜索树的属性，可以通过简单的递归算法(称为inorder -tree - walk，由inorder -tree - walk过程给出)按排序顺序打印出二叉搜索树中的所有键。

这个算法之所以如此命名，是因为它在打印左子树的值和打印右子树的值之间打印子树根的键。

![img](https://upload-images.jianshu.io/upload_images/28077103-71cf0848ecbdbba2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

要打印二叉搜索树T中的所有元素，请调用INORDER-TREEWALK(T.root)。例如，序树遍历按照2、5、5、6、7、8的顺序打印例1和例2中的两个二叉搜索树中的键。

