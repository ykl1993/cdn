# SetHttpsOptionConfig {#doc_api_Cdn_SetHttpsOptionConfig .reference}

调用SetHttpsOptionConfig接口设置域名的HTTP2.0开关。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetHttpsOptionConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetHttpsOptionConfig|操作接口名，系统规定参数。取值：**SetHttpsOptionConfig**。

 |
|DomainName|String|是|xxx|域名。

 |
|Http2|String|是|on|HTTP2.0开关。取值：

 -   **on**
-   **off**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|6649A92B-F105-48A0-BC94-E5BB38570652|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetHttpsOptionConfig
&DomainName=xxx
&Http2=on
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>6649A92B-F105-48A0-BC94-E5BB38570652</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"6649A92B-F105-48A0-BC94-E5BB38570652",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|HttpsNotEnabled|Please open https first.|请先开通HTTPS安全加速功能。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

