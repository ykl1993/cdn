# DescribeDomainRealTimeByteHitRateData {#doc_api_Cdn_DescribeDomainRealTimeByteHitRateData .reference}

调用DescribeDomainRealTimeByteHitRateData接口获取域名1分钟粒度字节命中率数据。

-   可以查询7天内的数据，单次查询**StartTime**和**EndTime**跨度不能超过24小时。
-   如果**StartTime**和**EndTime**均未指定，默认返回当前时间起一小时内的数据。

**说明：** 由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeByteHitRateData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRealTimeByteHitRateData|操作接口名，系统规定参数。取值：**DescribeDomainRealTimeByteHitRateData**。

 |
|DomainName|String|是|test.test.com|加速域名

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从**StartTime**起一小时内的数据。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从**EndTime**起一小时内的数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |返回数据

 |
|└ByteHitRate|Float|0.8956940476262277|字节命中率数据

 |
|└TimeStamp|String|2016-10-20T04:00:00Z|数据时间戳。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainRealTimeByteHitRateData
&DomainName=test.test.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>3FAF1DD8-3CD9-4C37-A5D5-172DB33F4614</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"3FAF1DD8-3CD9-4C37-A5D5-172DB33F4614",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|开始时间或结束时间格式错误。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

