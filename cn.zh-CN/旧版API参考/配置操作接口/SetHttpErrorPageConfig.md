# SetHttpErrorPageConfig {#doc_api_Cdn_SetHttpErrorPageConfig .reference}

调用SetHttpErrorPageConfig接口设置加速域名自定义错误页面跳转。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetHttpErrorPageConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetHttpErrorPageConfig|操作接口名，系统规定参数。取值：**SetHttpErrorPageConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|ErrorCode|String|是|500|自定义错误码。

 |
|PageUrl|String|是|http%3A%2F%2Fwww.aliyun.com%2Fnotfound%2F|自定义发生错误后跳转到页面URL（该加速域名下的完整路径）。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetHttpErrorPageConfig
&DomainName=www.macaron.org.cn
&ErrorCode=500
&PageUrl=http%3A%2F%2Fwww.aliyun.com%2Fnotfound%2F
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F</RequestId>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|MissingParameter|The specified value of parameter ErrorCode can not be empty.|参数ErrorCode不能为空。|
|400|MissingParameter|The specified value of parameter PageUrl can not be empty.|参数PageUrl不能为空。|
|400|InvalidPageUrl.Malformed|The specified value of parameter PageUrl is not malformed.|参数PageUrl格式错误。|
|400|InvalidErrorCode.Malformed|The specified value of parameter ErrorCode is not malformed.|参数ErrorCode 格式错误。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

