# DescribeRefreshTasks {#reference3132 .reference}

查询刷新、预热状态是否在全网生效。

-   支持根据任务ID查询、URL查询。
-   Taskid与Objectpath都不指定，默认查3天内，第一页的数据（20条）。
-   Taskid与Objectpath可以同时指定。
-   当指定DomainName或TaskStatus时，ObjectType该项为必填。
-   只可查询3天内的数据。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeRefreshTasks。|
|TaskId|String|否|按任务Id查询刷新状态。|
|ObjectPath|String|否|按路径查询，准确匹配。|
|DomainName|String|否|域名。|
|ObjectType|String|否|任务类型。包括：-   file
-   directory
-   preload

当指定DomainName或TaskStatus时，该项为必填。|
|Status|String|否|任务状态。包括：-   Complete：完成。
-   Refreshing：刷新中。
-   Failed：刷新失败。

|
|StartTime|String|否|开始时间。格式例如：2017-01-01T12:12:20Z。|
|EndTime|String|否|结束时间。格式例如：2017-01-01T12:12:20Z。|
|PageSize|Integer|否|分页大小。默认值：20。取值范围：1~50之前的任意整数。|
|PageNumber|Integer|否|取得第几页。取值范围：1~100000。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|Tasks|Struct|TaskItem组成的Task任务列表。|
|PageSize|Integer|整页大小。|
|PageNumber|Integer|页码。|
|TotalCount|Integer|总条数。|

## TaskItem 子节点 { .section}

|名称|类型|描述|
|--|--|--|
|TaskId|String|任务Id。|
|ObjectPath|String|刷新对象路径。|
|Status|String|状态。包括：-   Complete：完成。
-   Refreshing：刷新中。
-   Failed：刷新失败。
-   Pending：等待刷新。

|
|Process|String|进度百分比。|
|ObjectType|String|任务类型。包括：-   file
-   path
-   preload

|
|CreationTime|DateTime|任务对象创建时间，UTC时间。|
|Description|String|刷新预热失败返回错误描述。目前包含三种错误：-   Internal Error
-   Origin Timeout
-   Origin Return StatusCode 5XX

|

## 示例 { .section}

请求示例：

```
https://cdn.aliyuncs.com?&Action=DescribeRefreshTasks&ObjectPath=&PageNumber=1&PageSize=10&<公共请求参数>

```

返回示例：

JSON格式：

```language-json
{
	"Tasks" : {
		"CDNTask" : [{
				"CreationTime" : "2014-11-27T08:23:22Z",
				"ObjectPath" : "http://example1.com/1.txt",
				"Status" : "Complete",
				"TaskId" : "704225667",
                "ObjectType" : "file",
                "Process" : "100%"
			}, {
				"CreationTime" : "2014-11-27T08:18:38Z",
				"ObjectPath" : "http://example2.com/1.txt",
				"Status" : "Complete",
				"TaskId" : "704222904",
                "ObjectType" : "file",
                "Process" : "100%"
			}
		]
	},
	"PageNumber" : 1,
	"PageSize" : 10,
	"TotalCount" : 2,
	"RequestId" : "174F6032-AA26-470D-B90E-36F0EB205BEE"
}

```

## 错误码 { .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidTaskId.Malformed|Specified TaskId is malformed.|400|TaskId格式错误。|

公共错误码参见 [附录](../../../../dita-oss-bucket/SP_19/DNCDN11878652/ZH-CN_TP_5278.dita)。

