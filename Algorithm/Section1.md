# C1 算法在计算中的应用
## 1.1 算法

* 算法（algorithm）就是任何良定义的计算过程，取某个值或值的集合作为输入并产生某个值或值的集合作为输出。
* 有趣的算法共有两个特征：
	+ 存在许多候选解
	+ 存在实际应用
* 数据结构
	+ 数据结构是一种存储和组织数据的方式，旨在便于访问和修改。
* 技术
	+ 学习算法设计与分析的技术，以便能自行设计算法、证明其正确性和理解其效率。
* 难题
	+ NP完全问题
* 并行性
	+ 为了从多核计算机获得最佳的性能，设计算法时必须考虑并行性。

## 1.2 作为一种技术的算法

* 应该明智使用资源
* 效率
	+ 为求解相同问题而设计的不同算法在效率方面常常具有显著的差别。这些差别可能比由于硬件和软件造成的差别要重要得多。
* 算法与其他技术
	+ 算法是当代计算机中使用的大多数技术的核心。

# C2 算法基础
## 2.1 插入排序
### 插入排序过程
插入排序的工作方式像许多人排序一手扑克牌。开始时，我们左手为空并且桌子上的牌面向下。然后，我们每次从桌子上拿走一张牌并将它插入左手中正确的位置。
对于插入排序，我们将其伪代码过程命名为INSERTION-SORT，其中的参数一个数组*A\[1..n\]*，包含长度为*n*的要排序的一个序列。
```java
INSERTION-SORT(A) {
	for j = 2 to A.length
		key = A[j]
		// Insert A[j] into the sorted sequence A[1..j-1].
		i = j - 1
		while i > 0 and A[i] > key
			A[i+1] = A[i]
			i = i - 1
		A[i + 1] = key
}
```
### 插入排序算法的分析
* Correctness proof: loop-invariant（循环不变式）
* Asymptotic Analysis（渐进分析）

先给出每条语句的执行时间和执行次数

for j = 2 to A.length

![test](https://github.com/wobuhuicode/NoteHub/blob/master/Algorithm/image/%E4%B8%80%E5%AD%A3%E5%BA%A6.png?raw=true)

|行|代码|代价|次数
|:-:|:---|:--:|:--:|
|1|`for j = 2 to A.length`|![](http://latex.codecogs.com/gif.latex?c_1)|*n*|
|2|`key = A[j]`|![](http://latex.codecogs.com/gif.latex?c_2)|*n-1*|

## 2.2 分析
假定一种通用的单处理器计算模型--随机访问机（RAM）
