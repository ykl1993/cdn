# SetRefererConfig {#doc_api_Cdn_SetRefererConfig .reference}

调用SetRefererConfig接口设置加速域名的Refer防盗链功能。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetRefererConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetRefererConfig|操作接口名，系统规定参数。取值：**SetRefererConfig**。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|ReferType|String|是|block|refer类型。取值：

 -   **block**：黑名单
-   **allow**：白名单

 |
|DisableAst|String|否|off|是否精确匹配域名。取值：

 -   **on**：精确匹配，不自动匹配子域名。
-   **off**：模糊匹配，自动匹配子域名。
-   默认值：**off**。

 |
|AllowEmpty|String|否|on|是否允许空refer访问。取值：

 -   **on**：允许
-   **off**：不允许
-   默认值：**on**

 |
|ReferList|String|否|a.com,b.com|逗号隔开的域名列表。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetRefererConfig
&DomainName=www.yourdomain.com
&ReferType=block
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>7D5585DD-9340-41C7-A49D-EBBA06184960</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidAllowEmpty.ValueNotSupported</Code>
  <Message>The specified value of parameter AllowEmpty is not supported.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The specified value of parameter AllowEmpty is not supported.",
	"RequestId":"7D5585DD-9340-41C7-A49D-EBBA06184960",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidAllowEmpty.ValueNotSupported"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidReferType.ValueNotSupported|The specified value of parameter ReferType is not supported.|指定的ReferType类型不合法，超出可选范围。取值：block：黑名单；allow：白名单。|
|400|InvalidAllowEmpty.ValueNotSupported|The specified value of parameter AllowEmpty is not supported.|指定的refer是否允许为空不合法，超出可选范围。|
|400|InvalidReferList.Malformed|The specified value of parameter ReferList is malformed.|指定的域名列表ReferList不合法，格式错误。|
|400|InvalidDisableAst.ValueNotSupported|The specified value of parameter DisableAst is not supported.|不支持参数DisableAst。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

