# DescribeDomainRegionData {#doc_api_Cdn_DescribeDomainRegionData .reference}

调用DescribeDomainRegionData接口获取加速域名天粒度的用户区域分布数据统计。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRegionData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRegionData|操作接口名，系统规定参数。取值：**DescribeDomainRegionData** 。

 |
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表所有。

 |
|EndTime|String|否|2016-03-13|结束时间需大于起始时间，北京时间。

 格式为：YYYY-MM-DD。

 |
|StartTime|String|否|2016-03-13|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|86400|时间间隔

 |
|DomainName|String|test.test.com|加速域名

 |
|EndTime|String|2016-03-13|获取数据结束时间

 |
|RequestId|String|2E5AD83F-BD7B-462E-8319-2E30E305519A|请求id

 |
|StartTime|String|2016-03-13|获取数据起始时间

 |
|Value| | |value

 |
|└AvgObjectSize|String|800019.0|响应平均大小。单位：byte。

 |
|└AvgResponseRate|String|154.3345765545624|平均响应速度。单位：byte/秒。

 |
|└AvgResponseTime|String|5183.666666666667|平均响应时间。单位：毫秒。

 |
|└Bps|String|380.9614285714286|带宽

 |
|└ByteHitRate|String|100.0|字节命中率，如返回90即为90%。

 |
|└BytesProportion|String|0.003544181046236794|总流量占比，如返回90即为90%。

 |
|└Proportion|String|0.01155980271270037|访问占比数据，如返回90即为90%。

 |
|└Qps|String|5.9523809523809524E-5|每秒查询率

 |
|└Region|String|日本|地区信息

 |
|└RegionEname|String|japan|地区英文名称

 |
|└ReqErrRate|String|0.0|请求错误率，如返回90即为90%。

 |
|└ReqHitRate|String|100.0|请求命中率，如返回0.5即为0.5% 。

 |
|└TotalBytes|String|2400057|总流量

 |
|└TotalQuery|String|3|总请求次数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainRegionData
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>0A7E5641-7096-4A39-94C2-C379714D928C</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>Specified StartTime is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified StartTime is malformed.",
	"RequestId":"0A7E5641-7096-4A39-94C2-C379714D928C",
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

