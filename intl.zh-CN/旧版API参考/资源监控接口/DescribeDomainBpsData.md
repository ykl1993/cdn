# DescribeDomainBpsData {#doc_api_Cdn_DescribeDomainBpsData .reference}

调用DescribeDomainBpsData接口获取加速域名的网络带宽监控数据。

单位：bit/second。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。
-   使用该接口一次性查询全部地区和运营商的数据可能存在偏差。因此建议您使用该接口时，逐个地区、运营商地查询。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainBpsData|操作接口名，系统规定参数取值：**DescribeDomainBpsData**

 |
|DomainName|String|否|test.test.com|若参数为空，默认返回所有加速域名合并后数据

 可输入需要查询的加速域名

 支持批量域名查询，多个域名用逗号（半角）分隔

 |
|DomainType|String|否|dynamic|查询类型，传dynamic时，查询全站加速动态资源的实时带宽和静态资源的实时带宽。不传时查询静态资源的实时带宽

 |
|EndTime|String|否|2015-12-10T20:00Z|结束时间需大于起始时间；获日期格式按照ISO8601表示法，并使用UTC时间。

 格式为：YYYY-MM-DDThh:mmZ

 |
|Interval|String|否|300|查询数据的时间粒度，支持300, 3600, 14400, 28800和86400秒。不传和传的值不支持时，使用默认值300秒

 |
|IspNameEn|String|否|telecom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商

 |
|LocationNameEn|String|否|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域

 |
|StartTime|String|否|2015-12-10T20:00Z|获取数据起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。

 格式为：YYYY-MM-DDThh:mmZ

 最小数据粒度为5分钟

 不写默认读取过去24小时数据

 |
|TimeMerge|String|否|on|取值范围 **on**：默认值，每条记录的时间间隔会根据时间跨度做合并；**off**：返回5分钟粒度数据，最大时间跨度为31天

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BpsDataPerInterval| | |每个时间间隔的网络带宽数据

 |
|└DomesticL2Value|String|0|L2国内带宽bps，当按区域运营商查询时，此值为空

 |
|└DomesticValue|String|11286111|国内带宽bps，当按区域运营商查询时，此值为空

 |
|└DynamicDomesticValue|String|0|全站加速，国内带宽动态bps，当按区域运营商查询时，此值为空

 |
|└DynamicOverseasValue|String|0|全站加速，海外带宽动态bps，当按区域运营商查询时，此值为空

 |
|└DynamicValue|String|0|全站加速，动态bps数据值，单位：bit/second

 |
|└L2Value|String|0|L2 bps数据值，单位：bit/second

 |
|└OverseasL2Value|String|0|L2海外带宽bps，当按区域运营商查询时，此值为空

 |
|└OverseasValue|String|2000|海外带宽bps，当按区域运营商查询时，此值为空

 |
|└StaticDomesticValue|String|0|全站加速，国内带宽静态bps，当按区域运营商查询时，此值为空

 |
|└StaticOverseasValue|String|0|全站加速，海外带宽静态bps，当按区域运营商查询时，此值为空

 |
|└StaticValue|String|0|全站加速，静态bps数据值，单位：bit/second

 |
|└TimeStamp|String|2015-12-10T20:00:00Z|时间片起始时刻

 |
|└Value|String|11288111|bps数据值，单位：bit/second

 |
|DataInterval|String|300|需要补充时间间隔规则，每条记录的时间间隔，以秒为单位

 |
|DomainName|String|test.test.com|加速域名

 |
|EndTime|String|2015-12-10T20:00Z|结束时间

 |
|IspName|String|联通|运营商名称

 |
|IspNameEn|String|unicom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商

 |
|LocationName|String|北京市|区域名

 |
|LocationNameEn|String|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域

 |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|请求ID

 |
|StartTime|String|2015-12-10T20:00Z|开始时间

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com/?Action=DescribeDomainBpsData
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>246B5728-AEC1-4977-9F0D-0E4802A90023</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>Specified StartTime is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified StartTime is malformed.",
	"RequestId":"246B5728-AEC1-4977-9F0D-0E4802A90023",
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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

