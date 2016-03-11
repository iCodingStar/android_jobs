#### C++ 和 Java 区别
Java是更加纯粹的面向对象语言，很多设计模式都是从Java起源的。

相比C++，Java多了内存管理，正因为如此，Java在语言性能上就比C++要低一个档次。

#### 面向对象特性
继承，封装，多态

多态可以延伸一下，分为运行时多态和编译时多态。

编译时多态可以简单理解为函数重载和覆盖。

运行时多态可以理解为同样的接口的不同实现，运行的时候才确定要调用的方法的地址。


#### Java 的强弱软虚引用
强引用，宁愿抛出 OOM 也不进行内存回收。
弱引用，内存不足时进行回收。
软引用，每次 GC 时进行回收。
虚引用，随时会被回收。

对象可到达路径的判断，每条路径中取引用最弱的边，所有路径中去引用最强的边。

软引用和弱引用，需要 ```new SoftReference(Object)```
最好搭配```ReferenceQueue```来使用，在引用被回收的时候，有元素出队。

#### 二叉搜索树的插入查询复杂度
二叉搜索树的特性是，左子树的所有元素都比根节点小，右子树的所有元素都比根节点大。

根据这个特点，二叉搜索树的增查删的期望都等于树高，也就是 O(logN)。

#### 抽象类与接口的区别
这个不必多说，需要注意的是，Java 8 中，接口可以有默认实现，也就是非抽象方法。

#### ArrayList 与 LinkedList 区别
不说

#### Activity 的启动模式
Standard SingleTop SingleTask SingleInstance
这里注意一下 SingleTask 和 SingleInstance 的区别，前者所在的栈可以有多个 Activity，而后者只能有它一个 Activity。

#### Intent 的理解
对于 Intent ，最重要的莫过于隐式启动了。
- 可以有多个 intent-filter，只要有一个 intent-filter 匹配目标组件，便可以启动。
  - 可以有多个 action，但是不能没有，只要有其中一个能和目标组件匹配，该 intent-filter 便匹配。
  - 可以没有 category，但是一旦有 category 就必须全部跟目标组件匹配。系统会默认加上 DEFAUTE 这个 category。
  - 如果目标组件定义了 data，则 Intent 也必须要有至少一个对应的 data 。


