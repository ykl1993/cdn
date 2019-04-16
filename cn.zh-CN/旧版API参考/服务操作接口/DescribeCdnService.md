# DescribeCdnService {#doc_api_1013244 .reference}

调用DescribeCdnService接口查询CDN服务状态。

CDN服务状态包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeCdnService)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnService|操作接口名，系统规定参数，取值：**DescribeCdnService**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InternetChargeType|String|PayByTraffic|计费类型。

 -   **PayByTraffic**
-   **PayByBandwidth**

 |
|OpeningTime|String|2014-02-28T13:11:49Z|开通服务时间，ISO 8601时间格式。

 |
|ChangingChargeType|String|PayByTraffic|下次生效的计费类型。

 -   **PayByTraffic**
-   **PayByBandwidth**

 |
|ChangingAffectTime|String|2014-11-27T16:00:00Z|GMT时间。

 |
|OperationLocks| | |业务锁定状态，例如：欠费，安全等。

 |
|└LockReason|String|financial|业务锁定的原因。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |
|InstanceId|String|aliuid|实例ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCdnService
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <ChangingChargeType>PayByTraffic</ChangingChargeType>
  <OpeningTime>2016-12-14T02:34:12Z</OpeningTime>
  <InstanceId>1394881682333599</InstanceId>
  <RequestId>4D2605E0-F729-41FF-B553-8C4CB15D5808</RequestId>
  <ChangingAffectTime>2018-08-06T16:00:00Z</ChangingAffectTime>
  <OperationLocks/>
  <InternetChargeType>PayByTraffic</InternetChargeType>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OpeningTime":"2014-02-28T13:11:49Z",
	"ChangingChargeType":"PayByBandwidth",
	"RequestId":"BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23",
	"ChangingAffectTime":"2014-11-27T16:00:00Z",
	"OperationLocks":{
		"LockReason":[]
	},
	"InternetChargeType":"PayByTraffic"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|UnsupportedParameter|There is unsupported parameters|不支持该参数，请您检查该参数是否正确。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

