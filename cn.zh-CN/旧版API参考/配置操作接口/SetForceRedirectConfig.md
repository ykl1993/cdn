# SetForceRedirectConfig {#doc_api_Cdn_SetForceRedirectConfig .reference}

调用SetForceRedirectConfig接口设置强制访问跳转方式。

目前支持强制**Http**或**Https**跳转。

**说明：** 只有已经上传证书, 且证书被启用的情况下, 才能打开强制跳转功能。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetForceRedirectConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetForceRedirectConfig|操作接口名，系统规定参数。取值：**SetForceRedirectConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|加速域名。

 |
|RedirectType|String|是|Off|强制跳转类型。取值：

 -   **Off**
-   **Http**
-   **Https**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|D3861141-F245-4F7A-8388-6FC1E1F27F0B|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetForceRedirectConfig
&DomainName=www.macaron.org.cn
&RedirectType=Off
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>D3861141-F245-4F7A-8388-6FC1E1F27F0B</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"D3861141-F245-4F7A-8388-6FC1E1F27F0B",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidRedirectType.ValueNotSupported|The specified value of parameter RedirectType is not supported.|指定跳转类型有误，请重新选择。|
|400|InvalidOperation.ForceRedirect|Cannot perform this operation due to wrong business type or ssl status.|该域名无法设置强制跳转，请检查是否上传并启用了证书。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

