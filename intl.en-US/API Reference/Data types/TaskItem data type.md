# TaskItem data type {#reference_osd_z1t_vdb .reference}

The TaskItem data type.

## Node name {#section_z41_bbt_vdb .section}

TaskItem

## Subnodes {#section_nf4_bbt_vdb .section}

|Parameters|Type|Description|
|:---------|:---|:----------|
|TaskId|String|Task id.|
|ObjectPath|String|Refresh object path|
|Status|String|One of the status Pending | Refreshing | Failed | Complete. Pending: indicates the refresh is starting  Refreshing: refreshing Failed: refresh failed Complete: refresh successful|
|CreationTime|DateTime|Task item creation time, UTC time|

