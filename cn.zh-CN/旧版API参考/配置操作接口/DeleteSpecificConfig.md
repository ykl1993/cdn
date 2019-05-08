# DeleteSpecificConfig {#doc_api_Cdn_DeleteSpecificConfig .reference}

调用DeleteSpecificConfig接口删除加速域名的配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DeleteSpecificConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteSpecificConfig|操作接口名，系统规定参数。取值：**DeleteSpecificConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|ConfigId|String|是|2317|配置ID，多个用逗号隔开。

 |
|FunctionName|String|是|error\_page|功能名称。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DeleteSpecificConfig
&DomainName=www.macaron.org.cn
&ConfigId=2317
&FunctionName=error_page
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|此方法不支持。|
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|MissingParameter|The specified value of parameter FunctionName can not be empty.|参数FunctionName不能为空。|
|400|MissingParameter|The specified value of parameter ConfigId can not be empty.|参数ConfigId不能为空。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

