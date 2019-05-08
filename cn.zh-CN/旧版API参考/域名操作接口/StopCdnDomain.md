# StopCdnDomain {#doc_api_Cdn_StopCdnDomain .reference}

调用StopCdnDomain接口停用某个加速域名。

**说明：** 

-   停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。
-   若暂时不需要对某域名进行加速，推荐使用**StopDomain**接口，暂停域名加速效果。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=StopCdnDomain)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|StopCdnDomain|操作接口名，系统规定参数。取值：**StopCdnDomain**。

 |
|DomainName|String|是|www.yourdomain.com|需要接入CDN的域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=StopCdnDomain
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>2AAA40D1-76E4-4F9D-86F5-B7DC9FE20CE6</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"2AAA40D1-76E4-4F9D-86F5-B7DC9FE20CE6",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

