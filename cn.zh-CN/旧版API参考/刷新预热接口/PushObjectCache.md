# PushObjectCache {#doc_api_Cdn_PushObjectCache .reference}

调用PushObjectCache接口将源站的内容主动预热到L2 Cache节点上。

首次访问可直接命中缓存，缓解源站压力。支持post请求，参数用form表单。

限制条件：

-   同一个 ID 每天最多提交刷新预热类请求数量：URL：2000条；

    **说明：** 目前不支持目录级别的预热。

-   刷新预热类接口包含**RefreshObjectCaches** 刷新接口和 **PushObjectCache**预热接口。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=PushObjectCache)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PushObjectCache|操作接口名，系统规定参数。取值：**PushObjectCache**。

 |
|ObjectPath|String|是|abc.com/image/1.png|输入示例：abc.com/image/1.png，多个URL之间需要用换行符（\\n或\\r\\n）分隔。

 |
|Area|String|否|domestic|预热区域。取值：

 -   **domestic**
-   **overseas**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PushTaskId|String|95248880|预热返回的任务ID，多个任务ID用逗号（半角）分隔。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=PushObjectCache
&ObjectPath=abc.com/image/1.png	
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>43730243-DBE3-4A45-9F6E-99225221D0AD</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"43730243-DBE3-4A45-9F6E-99225221D0AD",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|QuotaExceeded.Refresh|You've exceeded the prescribed refresh limits.|超出当日刷新限制。今日刷新数已用完。您可以通过刷新接口查询今日的刷新次数。|
|400|InvalidObjectPath.Malformed|The specific value of parameter ObjectPath is malformed.|参数ObjectPath值格式错误。输入示例：abc.com/image/1.png。多个URL之间需要用换行符（\\n 或 \\r\\n）分隔。|
|400|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|该操作不支持泛域名。|
|403|PreloadQueueFull|Preload queue is full, please try again later!|预加载队列已满，请您稍后再试。|
|400|InvalidObjectPath.Size.Malformed|The size of ObjectPath is bigger than 1000.|预热url个数请勿超过1000.|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

