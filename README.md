# data-log


## 项目说明
 ### 都记录了什么？
 本项目用于记录数据的变更日志，每一条数据的变动都是由业务系统的操作来完成的，那本项目都记录了些什么信息呢？
 + 1.操作用户的信息
 + 2.操作的来源系统信息 app.id
 + 3.操作来源的url地址信息
 + 4.操作来源的ip地址及地址解析
 + 5.操作来源的时间
 + 6.操作来源的系统信息
 + 7.操作的入参出参等信息
 + 8.用户一次接口操作所涉及的数据变动的表、字段、原始值、变动后的值等信息
 
 ### 对应用系统的影响
 data-log的目标是对业务系统是零侵入性，因为会有收集信息，故而会适当的降低业务系统的并发量，但这个量基本上可忽略不计，data-log不会做复杂的逻辑处理。
 
 ### 如何引入data-log
 在java的spring应用程序系统中会很简单的就把data-log引入到系统中，在我们的maven依赖中加入
 
``` 
    		<dependency>
 		 	<groupId>com.aven</groupId>
	 		<artifactId>data-log</artifactId>
	 		<version>1.0.2</version>
	 	</dependency>
 ```
 
 在配置中开启关闭data-log的功能
 
 `aven.data-log.open=true`  默认是开启的
 
 1.可以关闭某些url的记录
 
 `aven.data-log.close.url=/mine/*;/user/*` 关闭形如/mine/xxx的url的记录
 
 2.可以关闭某些表的记录
 
 `aven.data-log.close.table=dl_user;dl_work` 只要填入表名即可
 
 
 
