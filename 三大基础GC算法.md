### 1.标记清除（Mark and Sweep）
首先从根开始将可能被引用的对象用递归的方式进行标记，然后将没有标记到的对象作为垃圾进行回收。

### 2.复制收集（Copy and Collection）
会将从根开始被引用的对象复制到另外的空间中，然后，再将复制的对象所能够引用的对象用递归的方式不断复制下去。
标记清除算法在分配了大量对象，并且其中只有一小部分存活的情况下，所消耗的时间会大大超过必要的值，这是因为在清除阶段还需要对大量死亡对象进行扫描。复制收集
算法就是为了克服标记清除算法上述缺点而产生的

### 3.引用计数（Reference Count）
在每个对象中保存该对象的引用计数，当引用发生增减时对计数进行更新。引用计数的增减，一般发生在变量赋值、对象内容更新、函数结束（局部变量不再被引用）等时间
点。当一个对象的引用计数变为0时，则说明它将来不会再被引用，因此可以释放相应的内存空间。
引用最大优点是实现简单,最大缺点是无法解决循环引用的问题
