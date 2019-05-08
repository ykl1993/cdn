# DescribeDomainReqHitRateData {#doc_api_Cdn_DescribeDomainReqHitRateData .reference}

调用DescribeDomainReqHitRateData接口获取加速域名的请求命中率（命中请求百分比）。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainReqHitRateData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainReqHitRateData|操作接口名，系统规定参数。取值：**DescribeDomainReqHitRateData**。

 |
|DomainName|String|否|www.yourdomain.com|需要查询的加速域名，只支持一个域名，不写代表所有。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|-   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300|查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|test.com|加速域名信息

 |
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间

 |
|EndTime|String|2015-12-10T21:00Z|结束时间

 |
|ReqHitRateInterval| | |每个时间间隔的请求命中百分占比

 |
|└TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻

 |
|└Value|String|100.0|详细使用数据

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainReqHitRateData
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>3F7037CA-578C-4D95-B039-155858725C2E</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>Specified StartTime is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified StartTime is malformed.",
	"RequestId":"3F7037CA-578C-4D95-B039-155858725C2E",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidStartTime.Malformed"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

