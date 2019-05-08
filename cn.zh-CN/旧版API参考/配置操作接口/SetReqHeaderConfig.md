# SetReqHeaderConfig {#doc_api_Cdn_SetReqHeaderConfig .reference}

调用SetReqHeaderConfig接口设置回源自定义头。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetReqHeaderConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetReqHeaderConfig|操作接口名，系统规定参数。取值：**SetReqHeaderConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|Key|String|是|testkey|回源自定义头key。

 |
|Value|String|是|testvalue|回源自定义头value。

 |
|ConfigId|Long|否|123|配置ID，修改指定id的配置。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetReqHeaderConfig
&DomainName=www.macaron.org.cn
&Key=testkey
&Value=testvalue
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>3BCEEBE4-ADA4-49A1-BFAC-9D9F43937DBA</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"3BCEEBE4-ADA4-49A1-BFAC-9D9F43937DBA",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|MissingParameter|The specified value of parameter Key can not be empty.|Key不能为空。|
|400|MissingParameter|The specified value of parameter Value can not be empty.|该参数值不能为空。|
|400|InvalidKey.Malformed|The specified value of parameter Key is not malformed.|参数Key 格式错误。|
|400|InvalidValue.Malformed|The specified value of parameter Value is not malformed.|参数值错误。|
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|指定的HTTP头参数不合法，超出可选范围。取值：Content-Type,Cache-Control,Content-Disposition,Content-Language,Expires,Access-Control-Allow-Origin,Access-Control-Allow-Methods,Access-Control-Allow-Headers,Access-Control-Max-Age,Access-Control-Expose-Headers,Access-Control-Allow-Credentials。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

