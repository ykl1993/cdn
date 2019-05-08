# DescribeDomainsUsageByDay {#doc_api_Cdn_DescribeDomainsUsageByDay .reference}

调用DescribeDomainsUsageByDay接口获取加速域名天粒度监控统计数据。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainsUsageByDay)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainsUsageByDay|操作接口名，系统规定参数。取值：**DescribeDomainsUsageByDay**。

 |
|DomainName|String|否|www.yourdomain.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   使用北京时间。
-   格式为：YYYY-MM-DD。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|-   结束时间需大于起始时间。
-   使用北京时间。
-   格式为：YYYY-MM-DD。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C88EF8ED-72F0-45EA-9E86-95114E224FC5|请求ID

 |
|DomainName|String|test.com|加速域名信息

 |
|DataInterval|String|86400|每条记录的时间间隔，固定值1天。

 |
|StartTime|String|2015-12-01|开始时间

 |
|EndTime|String|2015-12-02|结束时间

 |
|UsageByDays| | |每个时间间隔统计数据

 |
|└BytesHitRate|String|97.46250599529726|命中率

 |
|└TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻

 |
|└Qps|String|7.466354166666667|每秒访问量

 |
|└RequestHitRate|String|70.24770071912111|请求命中率

 |
|└MaxBps|String|1.050307709E8|带宽峰值

 |
|└MaxBpsTime|String|2015-12-01 01:20|带宽峰值时刻

 |
|└MaxSrcBps|String|2015-12-01 22:30|回源带宽峰值

 |
|└TotalAccess|String|645093|总访问量

 |
|└MaxSrcBpsTime|String|2015-12-01 22:30|回源带宽峰值时刻

 |
|└TotalTraffic|String|564300099309|总流量

 |
|UsageTotal| | |汇总数据

 |
|└BytesHitRate|String|97.03110726801242|命中率

 |
|└RequestHitRate|String|69.92610837438424|请求命中率

 |
|└MaxBps|String|1.0747912780000001E8|带宽峰值

 |
|└MaxBpsTime|String|2015-12-02 23:55|带宽峰值时刻

 |
|└MaxSrcBps|String|2015-12-02 17:20|回源带宽峰值

 |
|└TotalAccess|String|1319500|总访问量

 |
|└MaxSrcBpsTime|String|2015-12-02 17:20|回源带宽峰值时刻

 |
|└TotalTraffic|String|1117711832100|总流量

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainsUsageByDay
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>7EF60FAD-87CF-47EE-BDBC-C8A34555CB50</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>Specified StartTime is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified StartTime is malformed.",
	"RequestId":"7EF60FAD-87CF-47EE-BDBC-C8A34555CB50",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidStartTime.Malformed"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

