# link-prediction
基于PySpark和MySQL实现复杂网络的（错误）链路预测。结合PySpark的RDD操作实现图的出入度、某两个节点的共同邻居等的计算。

Spark配置：

* scala-2.11.5
* spark-1.2.0
* jdk1.8.0_31

虽然现在Spark版本迭代更新很快，但对于初学PySpark的同学，本项目仍有一定参考价值。

参考论文:

* 吕琳媛. 复杂网络链路预测[J]. 电子科技大学学报, 2010, 39(5):651-661.

>相比NetworkX，结合Spark的图计算能更快一些，由于PySpark里没有GraphX模块，所以基于RDD的基本操作算子，自己实现一些图的基本计算。

## Data
6个CSV文件，对应6个复杂网络（三种网络：Internet网络、生物信息网络、社交媒体网络，每种网络有两个。即总共3个有向图网络，3个无向图网络），数据存储的形式是边集数组。
* 对于有向图来说，每行数据有两个元素表示一条有向边arc。第一个元素是该边的起始节点，第二个元素是该边的终点；
* 对于无向图来说，每行数据也是两个元素，代表组成该无向边edge的两个节点。
代码有一段是将数据从CSV文件中读取并保存在MySQL中。


## Algorithm
方法记录见[个人博客](http://yuenshome.space)之[《复杂网络链路预测》](http://yuenshome.space/?p=3753)。这篇笔记记录是对该文的学习总结，本项目主要实现了基于相似性的链路预测部分的算法。

参考论文:

* 吕琳媛. 复杂网络链路预测[J]. 电子科技大学学报, 2010, 39(5):651-661.

