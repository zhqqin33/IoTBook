# CTP帧结构
### CTP路由帧
CTP协议通过交换路由帧构建路由拓扑，并通过数据帧向汇聚节点传递感知数据。CTP路由帧结构如图5-42所示。

•	P（1 bit）：路由信息请求标志位。P置位用于节点向其它节点请求路由信息。如果一个节点收到P置位的路由帧，则该节点需要发送自己的路由帧。
•	C（1 bit）：拥塞标志位。 如果节点CTP数据帧发生丢失，则必须在它发送的下一个数据帧上将C位置位。
•	Parent：路由帧发送节点当前的父节点。
•	ETX: 发送节点的路径ETX。


<div align=center>
<img src=".\pics\fig-5-CTP路由帧结构.png" width="50%">

图5-42 CTP路由帧结构
</div>

### CTP数据帧
CTP数据帧结构如图5-43所示。

•	P: 路由信息请求标志位。
•	C：拥塞标志位。
•	THL: Time Has Lived, 数据包生存时间。数据包生成时为0, 每经过一跳增加1。
•	ETX: 发送或转发节点的路径ETX。当节点发送或转发CTP数据帧时，设置该字段。 如果一个节点收到的数据包中的ETX低于自己的路径ETX，那就意味着路由信息需要更新，它将发送路由帧来更新路由信息。
•	Origin:  生成数据包的源节点ID。在数据包传
•	SeqNo: 数据包在源节点上的序列号。源节点设置此字段，转发数据帧的节点不得修改它。
•	CollectionID: 更高层次的协议标识符。源节点设置此字段，转发数据帧的节点不得修改它。

<div align=center>
<img src=".\pics\fig-5-CTP数据帧结构.png" width="50%">

图5-43 CTP数据帧结构
</div>



