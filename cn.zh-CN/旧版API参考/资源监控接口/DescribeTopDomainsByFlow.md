# DescribeTopDomainsByFlow {#doc_api_Cdn_DescribeTopDomainsByFlow .reference}

调用DescribeTopDomainsByFlow接口获取用户按流量排名的域名。

-   不指定**StartTime**和**EndTime**时，默认读取当月的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeTopDomainsByFlow)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeTopDomainsByFlow|操作接口名，系统规定参数。取值：**DescribeTopDomainsByFlow**。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|-   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Limit|Long|否|20|域名获取数量限制。

 -   取值范围：1~100
-   默认值：20

 |
|Product|String|否|CDN|产品名称。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟，不写默认读取当月数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70|请求ID

 |
|StartTime|String|2016-03-01T04:00Z|开始时间

 |
|EndTime|String|2016-03-14T07:34Z|结束时间

 |
|TopDomains| | |排名域名列表

 |
|└DomainName|String|test.test.com|域名

 |
|└Rank|Long|1|排名

 |
|└TotalTraffic|String|2043859876683.9001|总流量

 |
|└TrafficPercent|String|30.64191989360235|流量占比

 |
|└MaxBps|Float|22139626|带宽峰值

 |
|└MaxBpsTime|String|1457111400|带宽峰值时刻

 |
|└TotalAccess|Long|107784230|访问次数

 |
|DomainCount|Long|68|账户下域名总数

 |
|DomainOnlineCount|Long|68|账户下“正在运行”域名总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <DomainCount>6</DomainCount>
  <DomainOnlineCount>6</DomainOnlineCount>
  <RequestId>AA553691-0A16-4CB4-B0A6-F209152B13AF</RequestId>
  <TopDomains>
    <TopDomain>
      <MaxBps>153.29600000000002</MaxBps>
      <Rank>1</Rank>
      <TrafficPercent>99.99526940725673</TrafficPercent>
      <TotalTraffic>21138</TotalTraffic>
      <TotalAccess>22</TotalAccess>
      <DomainName>baodu.com</DomainName>
      <MaxBpsTime>2019-04-15T20:30:00Z</MaxBpsTime>
    </TopDomain>
  </TopDomains>
  <EndTime>2019-04-29T16:00:00Z</EndTime>
  <StartTime>2019-03-31T16:00:00Z</StartTime>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DomainCount":6,
	"DomainOnlineCount":6,
	"RequestId":"AA553691-0A16-4CB4-B0A6-F209152B13AF",
	"EndTime":"2019-04-29T16:00:00Z",
	"TopDomains":{
		"TopDomain":[
			{
				"Rank":1,
				"MaxBps":"153.29600000000002",
				"TotalTraffic":21138,
				"TrafficPercent":"99.99526940725673",
				"TotalAccess":22,
				"DomainName":"baodu.com",
				"MaxBpsTime":"2019-04-15T20:30:00Z"
			}
		]
	},
	"StartTime":"2019-03-31T16:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

