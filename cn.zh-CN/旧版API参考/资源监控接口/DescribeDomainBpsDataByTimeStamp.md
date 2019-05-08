# DescribeDomainBpsDataByTimeStamp {#doc_api_Cdn_DescribeDomainBpsDataByTimeStamp .reference}

调用DescribeDomainBpsDataByTimeStamp接口获取加速域名的在某个时刻不同Locate和Isp上的带宽数据。

单位：bit/second。

-   不支持批量域名查询
-   时间精确到5分钟粒度

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsDataByTimeStamp)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainBpsDataByTimeStamp|操作接口名，系统规定参数。取值：**DescribeDomainBpsDataByTimeStamp**。

 |
|DomainName|String|是|www.yourdomain.com|要查询的域名，不能为空。

 |
|IspNames|String|是|unicom,telecom|需要查询目标Isp列表。

 -   用“,”隔开，不能为空。
-   ISP名通过**DescribeCdnRegionAndIsp**接口获得。

 |
|LocationNames|String|是|liaoning,guangxi|需要查询目标区域列表。

 -   用“,”隔开，不能为空。
-   Location名通过**DescribeCdnRegionAndIsp**接口获得。

 |
|TimePoint|String|是|2016-08-01T22:00Z|查询目标时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|abc.cn|加速域名信息

 |
|BpsDataList| | |每个Locate、ISP对应的bps值

 |
|└LocationName|String|Liaoning|节点名

 |
|└IspName|String|unicom|Isp名

 |
|└Bps|Long|52119553|对应的带宽值

 |
|└TimeStamp|String|2017-12-22T08:00:00:00Z|时刻

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时刻

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByTimeStamp
&DomainName=www.yourdomain.com
&IspNames=unicom,telecom
&LocationNames=liaoning,guangxi
&TimePoint=2016-08-01T22:00Z
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>B7C6F7EE-F862-491C-9944-0EC64B1D4D75</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidLocationNames.Malformed</Code>
  <Message>Specified LocationNames is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified LocationNames is malformed.",
	"RequestId":"B7C6F7EE-F862-491C-9944-0EC64B1D4D75",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidLocationNames.Malformed"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

