# Taskitem数据类型 {#reference_osd_z1t_vdb .reference}

TaskItem数据的类型。

## 节点名 {#section_z41_bbt_vdb .section}

TaskItem

## 子节点 {#section_nf4_bbt_vdb .section}

|名称|类型|描述|
|:-|:-|:-|
|TaskId|String|任务Id。|
|ObjectPath|String|刷新对象路径|
|Status|String|Pending | Refreshing | Failed | Complete状态中的一个。Pending：表示启动刷新中 Refreshing：刷新中 Failed： 刷新失败Complete：刷新成功|
|CreationTime|DateTime|任务对象创建时间，UTC时间|

