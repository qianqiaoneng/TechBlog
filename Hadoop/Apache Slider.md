## Apache Slider 学习笔记

### 什么是Apache Slider?

Apache Slider 本身是一个应用，也许可以理解成一个工具，作用是把一个分布式的应用部署到一个Apache Hadoop YARN管理的集群上，并监控这个应用在集群上的运行，随时启动，暂停和关闭应用实例，从而使得应用的实例规模可以随需所变。

### 为什么需要Apache Slider?

当越来越多的数据被搬到Hadoop集群上之后，越来越多的应用和服务就需要被就近部署在Hadoop集群上。Hadoop不再只是一个数据处理集群，还应该是一个能够提供服务的集群。利用Hadoop集群提供分布式服务，就自然而然要使用YARN作为应用服务的调度管理系统。YARN默认只是调度Hadoop Job，而Slider就是使YARN能够支持其他非Map Reducer任务的调度管理。

### Slider VS Yarn

Slider本质上一个定制过的YARN的Application Master，只不过这个application Master管理的application就是Slider用户的分布式应用。而YARN自带的Application Master管理的是Map Reduce Job。Slider就是利用YRAN管理Map Reduce Job的机制来管理Slider用户的分布式应用。

除此之外，Slider还有一个Hadoop客户端，通过rpc和restful API来调用Hadoop的HDFS文件系统，YARN的Resource Manager和Slider Application Master的服务。

...

Apache, Hadoop, Slider and the Hadoop elephant and Apache project logos are either registered trademarks or trademarks of the [Apache Software Foundation](http://www.apache.org/) in the United States or other countries.