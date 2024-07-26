### 起源:
> Voovan开源项目启动于2015年,始于自己在使用 Netty 和 Mina 时有较多难以理解的部分，同时在使用过程中遇到对粘包等问题的困扰，后来经过不断的对源码的学习以及对 java 异步通信的深入理解发现自 java 1.7以后 JDK 提供了更优秀的异步通信模型 AIO,随后决定自己参照 AIO 模型重新造一个轮子, 随后在 V4.0 版本将通信架构进行了重构, 放弃 AIO 转而采用 nio 模型重新实现（移除了原来的AIO 和 NIO 实现）, 在实现方式和关键的 io 调度部分有自己的思考, 和 netty 等基于 nio 的通信框架有明显的设计和架构上的区别。在开发的过程中对使用到的各类工具方法等做了整理，形成了一个常用并且简单易用的工具包。


### 特点:
> 极其简单易用的工具类和方法设计、几乎没有任何学习成本、支持 TLS/SSL 通信、连接池自管理、针对粘包处理支持，轻松处理Socket 通信过程中的粘包问题。
换句话说，有些情况下你仅仅需要一个 voovan 的包就可以实现并且完成你从开发到部署的整个过程。不需要在去熟悉使用其他第三方框架。

### V4.0.0:
 - 通信架构上进行了完全重构, 采用 nio 模型重新实现（移除了原来的AIO 和 NIO 实现）, 在实现方式和关键的 io 调度部分有自己的思考, 和 netty 等基于 nio 的通信框架有明显的设计和架构上的区别.
 - Web 服务的 http 编解码算法采用了新的算法,使其根据性能上的优势, 同时并没有因为参加 tfb 测试而放弃一些通用 Web 服务框架所因互备功能。并且已经在几个大型的区块链交易所推广使用承载用户资产折合价值数以亿计，并且支撑了在各种活动场景下的高并发场景，完全具备生产能力。
 - JDBC 部分新增了跨库事务绑定功能，同步驱动多个库的事务。并且提供 Recoder 以及 Dao 的操作方式大大提高了开发效率并且经过了严苛生产环境下的考验。
 - 工具类增加众多的方法，具体请异步相关文档