### 单进程单线程的Redis如何能够高并发

[单进程单线程的Redis如何能够高并发](https://blog.csdn.net/liupeng_qwert/article/details/77263187)

### 扩展

以下也是你应该知道的几种模型，祝你的面试一臂之力！

1、单进程多线程模型：MySQL、Memcached、Oracle（Windows版本）；

2、多进程模型：Oracle（Linux版本）；

3、Nginx有两类进程，一类称为Master进程(相当于管理进程)，另一类称为Worker进程（实际工作进程）。启动方式有两种：

（1）单进程启动：此时系统中仅有一个进程，该进程既充当Master进程的角色，也充当Worker进程的角色。

（2）多进程启动：此时系统有且仅有一个Master进程，至少有一个Worker进程工作。

（3）Master进程主要进行一些全局性的初始化工作和管理Worker的工作；事件处理是在Worker中进行的。

![这里写图片描述](https://img-blog.csdn.net/20180307172918264?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMDg3MDUxOA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### 当数据大于Redis内存时，Redis做了什么操作

 [Redis性能问题排查解决手册(七)](https://www.cnblogs.com/mushroom/p/4738170.html)
