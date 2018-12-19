# CreateUserUsageDataExportTask {#reference871 .reference}

创建账号历史用量数据导出任务, 将历史用量生成PDF文件用于下载。

**说明：** 最长可创建查询近1年数据的任务，单次导出任务跨度最长为1个月。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：CreateUserUsageDataExportTask。|
|StartTime|String|是|获取数据起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ 最小数据粒度为5分钟。|
|EndTime|String|是|结束时间需大于起始时间；获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。|
|TaskName|String|否|任务名称。|
|Type|String|是|需要获取的用量类型：flow或vas。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|TaskId|String|任务ID。|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=CreateUserUsageDataExportTask&Type=flow
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>


```

