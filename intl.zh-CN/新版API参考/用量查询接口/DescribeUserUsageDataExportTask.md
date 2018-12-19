# DescribeUserUsageDataExportTask {#reference1729 .reference}

列出用户最近三个月的用量导出任务信息。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeUserUsageDataExportTask。|
|PageSize|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|PageNumber|String|否|创建任务起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。不写默认读取过去24小时数据。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|TotalCount|String|总记录数。|
|PageSize|String|每页记录数。|
|PageNumber|DateTime|当前页。|
|UsageDataPerPage|UsageData\[\]|每页的用量数据。|

## UsageData { .section}

|名称|类型|描述|
|:-|:-|:-|
|StartTime|String|用量起始时刻。|
|EndTime|String|用量结束时间。|
|CreateTime|String|任务创建时间。|
|UpdateTime|String|任务最后更新时间。|
|Status|String|任务状态。|
|DownloadUrl|String|下载地址。|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=DescribeUserUsageDataExportTask&DomainName=example.com
&PageSize=10
&PageNumber=1
&<公共请求参数>


```

返回示例：

JSON格式

```
{
    "TotalCount": "1",
    "PageSize": "10",
    "PageNumber": "1",
    "UsageDataPerPage": {
        "UsageData": [
            {
                "StartTime": "2017-12-10T00:00:00Z",
                "EndTime": "2017-12-11T00:00:00Z",
                "CreateTime": "2017-12-15T12:33:10Z",
                "ModifyTime": "2017-12-15T12:38:49Z",
                "Status": "Success",
                "DownloadUrl":"http://example.com/xxxx/xxxx.pdf"
            }
        ]
    },
    "RequestId": "B955107D-E658-4E77-B913-E0AC3D31693E"
}
```

