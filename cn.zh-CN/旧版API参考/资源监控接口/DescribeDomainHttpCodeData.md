# DescribeDomainHttpCodeData {#doc_api_Cdn_DescribeDomainHttpCodeData .reference}

调用DescribeDomainHttpCodeData接口获取加速域名最小5分钟粒度的HTTP返回码占比数据。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainHttpCodeData|操作接口名，系统规定参数。取值：**DescribeDomainHttpCodeData** 。

 |
|DomainName|String|否|test.test.com|需要查询的加速域名，支持批量，多个域名用逗号（半角）分隔。

 |
|EndTime|String|否|2015-11-30T05:40Z|-   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300|查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒 。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-11-30T05:33Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |
|TimeMerge|String|否|on|取值：

 -   **on**：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   **off**：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|时间间隔

 |
|DomainName|String|test.test.com|域名

 |
|EndTime|String|2015-11-30T05:40Z|结束时间

 |
|HttpCodeData| | |数据

 |
|└TimeStamp|String|2015-11-30T05:30:00Z|时间戳

 |
|└Value| | |value

 |
|└Code|String|200|http返回码

 |
|└Count|String|300|总数

 |
|└Proportion|String|66.046511627907|占比使用数据

 |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|请求ID

 |
|StartTime|String|2015-11-30T05:33Z|开始时间

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainHttpCodeData
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>A1F901ED-C41B-4CE0-9DA4-73692F3A13CF</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"A1F901ED-C41B-4CE0-9DA4-73692F3A13CF",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

