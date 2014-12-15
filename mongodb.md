1. 看那些资料？
2. 使用场景？
2. 为什么快？
3. 怎么用？

**官网：**[http://www.mongodb.org/](http://www.mongodb.org/ "http://www.mongodb.org/")

**线上演示：**[http://try.mongodb.org/?_ga=1.226797589.962565127.1417832597](http://try.mongodb.org/?_ga=1.226797589.962565127.1417832597 "http://try.mongodb.org/?_ga=1.226797589.962565127.1417832597")

**中文手册：**[http://docs.mongoing.com/manual-zh/](http://docs.mongoing.com/manual-zh/ "http://docs.mongoing.com/manual-zh/")

**建议学习使用地址：**[http://www.w3cschool.cc/mongodb/mongodb-databases-documents-collections.html](http://www.w3cschool.cc/mongodb/mongodb-databases-documents-collections.html "http://www.w3cschool.cc/mongodb/mongodb-databases-documents-collections.html")


视觉中国的MongoDB应用实践
    [http://wenku.baidu.com/link?url=McLuByrx5MQfFrmZGBP7oGd1GlsMKiqMP1tMPzujyYcdSjs6_q0uqnnva2xev_5rhPAYCikR5XZ6YkBFBbgrM7TETf2-223iYr3Zqhy9P9G](http://wenku.baidu.com/link?url=McLuByrx5MQfFrmZGBP7oGd1GlsMKiqMP1tMPzujyYcdSjs6_q0uqnnva2xev_5rhPAYCikR5XZ6YkBFBbgrM7TETf2-223iYr3Zqhy9P9G "http://wenku.baidu.com/link?url=McLuByrx5MQfFrmZGBP7oGd1GlsMKiqMP1tMPzujyYcdSjs6_q0uqnnva2xev_5rhPAYCikR5XZ6YkBFBbgrM7TETf2-223iYr3Zqhy9P9G")

在搜索引擎中：

    mongodb site:www.cnblogs.com

    视觉中国的MongoDB应用实践 filetype:pdf

![](http://images.cnitblog.com/i/339094/201407/171531576463891.png)

![](http://up.2cto.com/2012/0413/20120413102028731.jpg)

可以使用js  和关系型数据库的存储过程差不多 可以用来造数据

**内存映射存储引擎**

MongoDB目前支持的存储引擎为内存映射引擎。当MongoDB启动的时候，会将所有的数据文件映射到内存中，然后操作系统会托管所有的磁盘操作。这种存储引擎有以下几种特点：

* MongoDB中关于内存管理的代码非常精简，毕竟相关的工作已经有操作系统进行托管。

* MongoDB服务器使用的虚拟内存将非常巨大，并将超过整个数据文件的大小。不用担心，操作系统会去处理这一切。

* MongoDB无法控制数据写入磁盘的顺序，这样将导致MongoDB无法实现writeahead日志的特性。所以，如果MongoDB希望提供一种durability的特性（这一特性可以参考我写的关于Cassandra文章：http://www.cnblogs.com/gpcuster/tag/Cassandra/），需要实现另外一种存储引擎。

* 32位系统的MongoDB服务器每一个Mongod实例只能使用2G的数据文件。这是由于地址指针只能支持32位。


**分片：**

分片的目的

高数据量和吞吐量的数据库应用会对单机的性能造成较大压力,大的查询量会将单机的CPU耗尽,大的数据量对单机的存储压力较大,最终会耗尽系统的内存而将压力转移到磁盘IO上.

为了解决这些问题,有两个基本的方法: 纵向扩展 和 分片 .

RSS阅读：
