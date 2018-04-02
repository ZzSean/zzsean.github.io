---

layout:     post

title:      "Notes of Python - PriorityQueue"

subtitle:   " 优先队列和堆 "

date:       2018-04-02 20:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: false

tags:

    - python

---




Python学习笔记---优先队列和堆|

## 堆(heapq)：  

python里面的堆是通过在列表中维护堆的性质实现的。这一点与C++中heap一系列的算法类似，底层是通过堆vector的维护获取堆的性质。

``` python
import heapq
#向堆中插入元素，heapq会维护列表heap中的元素保持堆的性质
heapq.heappush(heap, item)
#heapq把列表x转换成堆
heapq.heapify(x)
#从可迭代的迭代器中返回最大的n个数，可以指定比较的key
heapq.nlargest(n, iterable[, key])
#从可迭代的迭代器中返回最小的n个数，可以指定比较的key
heapq.nsmallest(n, iterable[, key])
#从堆中删除元素，返回值是堆中最小或者最大的元素
heapq.heappop(heap)
```



## PriorityQueue：

从源代码可以看出来，PriorityQueue使用的就是heapq来实现的，所以可以认为两者算法本质上是一样的。当然PriorityQueue考虑到了线程安全的问题。 
下面给出PriorityQueue的部分API和使用方法。 

``` python
#向队列中添加元素
Queue.put(item[, block[, timeout]])
#从队列中获取元素(从小到大)
Queue.get([block[, timeout]])
#队列判空
Queue.empty()
#队列大小
Queue.qsize()
```

