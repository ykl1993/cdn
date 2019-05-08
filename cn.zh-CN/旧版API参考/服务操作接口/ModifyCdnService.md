# ModifyCdnService {#doc_api_Cdn_ModifyCdnService .reference}

调用ModifyCdnService接口变更CDN服务的计费类型。

-   需先开通才可执行此操作。
-   变更计费类型，次日00:00生效；多次变更以最新提交的为准。
-   计费类型：
    -   按峰值带宽计费
    -   按使用流量计费

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=ModifyCdnService)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyCdnService|系统规定参数，取值：**ModifyCdnService**。

 |
|InternetChargeType|String|是|PayByTraffic|开通服务的计费类型。

 -   按流量：**PayByTraffic**
-   按带宽峰值：**PayByBandwidth**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=ModifyCdnService
&InternetChargeType=PayByTraffic
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>C961B79B-237A-4E6F-B46C-1A0C0F8E743C</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>CSS_CHECK_UPDOWNGRADE_ERROR</Code>
  <Message>You have an order not yet effective</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"You have an order not yet effective",
	"RequestId":"C961B79B-237A-4E6F-B46C-1A0C0F8E743C",
	"HostId":"cdn.aliyuncs.com",
	"Code":"CSS_CHECK_UPDOWNGRADE_ERROR"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidParameter|The specified value of parameter "InternetChargeType" is not valid.|参数“InternetChargeType”的值无效。|
|400|InsufficientBalance|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_INVALID\_PAY\_METHOD|INVALID\_PAY\_METHOD|付款方式无效。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_HASORDER|You have an order not yet effective|您有未生效的订单。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

