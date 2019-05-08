# SetSourceHostConfig {#doc_api_Cdn_SetSourceHostConfig .reference}

调用SetSourceHostConfig接口设置回源host功能。

**说明：** 若源站为OSS域名，需将OSS域名设置为回源host（即源站域名），才能正常回源。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetSourceHostConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetSourceHostConfig|操作接口名，系统规定参数。取值：**SetSourceHostConfig**。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名

 |
|Enable|String|否|On|是否打开自定义host配置。取值：

 -   **on**
-   **off**

 默认值：**on**。

 |
|BackSrcDomain|String|否|www.aliyun.com|自定义回源域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetSourceHostConfig
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>28A26E4B-4D0C-4E1B-AF25-59125FCE8008</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidBackSrcDomain.Malformed</Code>
  <Message>Specified BackSrcDomain is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified BackSrcDomain is malformed.",
	"RequestId":"28A26E4B-4D0C-4E1B-AF25-59125FCE8008",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidBackSrcDomain.Malformed"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidParameter|The specified value of parameter "Enable" is not valid.|参数“Enable”的值无效。|
|400|MissingBackSrcDomain|The input parameter BackSrcDomain that is mandatory for processing this request is not supplied.|参数BackSrcDomain为必填。|
|400|InvalidBackSrcDomain.Malformed|Specified BackSrcDomain is malformed.|回源域名格式BackSrcDomain不合法。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

