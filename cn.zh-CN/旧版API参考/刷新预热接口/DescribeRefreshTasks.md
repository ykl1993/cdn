# DescribeRefreshTasks {#doc_api_Cdn_DescribeRefreshTasks .reference}

调用DescribeRefreshTasks接口查询刷新、预热状态是否在全网生效。

-   支持根据任务ID查询、URL查询。
-   **taskid**与**objectpath**都不指定，默认查7天内，第一页的数据（20条）。
-   **Taskid**与**objectpath**可以同时指定，逻辑与的关系。
-   只可查询7天内的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshTasks)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRefreshTasks|操作接口名，系统规定参数。取值：**DescribeRefreshTasks**。

 |
|DomainName|String|否|www.yourdomain.com|域名

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|结束时间。格式例如：2017-01-01T12:12:20Z。

 |
|ObjectPath|String|否|http://aaa.com/1.txt|按路径查询，准确匹配。

 |
|ObjectType|String|否|file|任务类型。

 -   **file**
-   **path**
-   **preload**

 当指定**DomainName**或**TaskStatus**时，该项为必填。

 |
|PageNumber|Integer|否|1|取得第几页。取值范围：1~100000。

 |
|PageSize|Integer|否|20|分页大小。

 -   取值范围：1~50之前的任意整数。
-   默认值：20。

 |
|ResourceGroupId|String|否|your resourceGroupId|资源组ID

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|开始时间。格式例如：2017-01-01T12:12:20Z。

 |
|Status|String|否|Complete|任务状态。

 -   **Complete**：完成
-   **Refreshing**：刷新中
-   **Failed**：刷新失败

 |
|TaskId|String|否|1234321|按任务ID查询刷新状态

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Tasks| | |TaskItem组成的Task任务列表。

 |
|└TaskId|String|704225667|任务Id。

 |
|└ObjectPath|String|http://aaa.com/1.txt|刷新对象路径

 |
|└Status|String|Complete|状态。取值：

 -   **Complete**：完成
-   **Refreshing**：刷新中
-   **Failed**：刷新失败
-   **Pending**：等待刷新

 |
|└Process|String|100%|进度百分比

 |
|└ObjectType|String|file|任务类型。

 -   **file**
-   **path**
-   **preload**

 |
|└CreationTime|String|2014-11-27T08:23:22Z|任务对象创建时间，UTC时间。

 |
|└Description|String|Internal Error|刷新预热失败返回错误描述，目前包含三种错误：

 -   **Internal Error**
-   **Origin Timeout**
-   **Origin Return StatusCode 5XX**

 |
|PageSize|Long|1|整页大小

 |
|PageNumber|Long|10|页码

 |
|TotalCount|Long|2|总条数

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeRefreshTasks
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>B233CAB7-5BD3-427A-B264-F2F788CE1D21</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>The specified StartTime is invalid.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The specified StartTime is invalid.",
	"RequestId":"B233CAB7-5BD3-427A-B264-F2F788CE1D21",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidStartTime.Malformed"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTaskId.Malformed|Specified TaskId is malformed.|TaskId无效。请检查 TaskId 是否存在。|
|400|MissingParameter|StartTime and EndTime can not be single.|开始时间与结束时间均为必填。|
|400|MissingParameter.ObjectType|If DomainName or Status is provided, ObjectType can not be empty.|参数“ObjectType”缺失。|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|请检查时间设置是否正确，结束时间不能小于或等于开始时间。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|
|400|InvalidStatus.ValueNotSupported|The specified value of parameter Status is not supported.|参数“Status”的值无效。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

