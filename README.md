#### golang 构建数据服务 </br>
##### 1.使用 xorm 或 gorm 实现本文的程序  </br>
个人选择了xorm实现该程序.关键代码如图所示 </br>
创建管理引擎 </br>
![Alt text](./pic/1511873815995.png) </br>
![Alt text](./pic/1511873834929.png) </br>
定义一个结构体和SYNC2数据库表结构 </br>
![Alt text](./pic/1511874033745.png) </br>
通过engine调用对应的方法管理数据库 </br>
![Alt text](./pic/1511874067099.png) </br>
![Alt text](./pic/1511874079434.png) </br>
测试结果 </br>
![Alt text](./pic/1511874889035.png) </br>
![Alt text](./pic/1511874937631.png) </br>
##### 2.从编程效率、程序结构、服务性能等角度对比 database/sql 与 orm 实现的异同 </br>
编程效率还是orm更快吧,毕竟不去调用database/sql的四个方法然后自己处理得到的返回值,orm还是相对方便一点. </br>
程序结构上也简化了,因为用不到dao.go,直接调用engine的方法就可以得到我们要的数据了 </br>
服务性能应该是database/sql比较好,毕竟orm是牺牲性能获得易用性 </br>
##### 3.orm 是否就是实现了 dao 的自动化？ </br>
是吧,orm 使得我们不需要编写 dao 服务 </br>
##### 4.使用ab测试性能 </br>
![Alt text](./pic/1511875426693.png) </br>
![Alt text](./pic/1511875454506.png) </br>
