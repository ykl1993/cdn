# SetRemoveQueryStringConfig {#doc_api_Cdn_SetRemoveQueryStringConfig .reference}

调用SetRemoveQueryStringConfig接口设置过滤参数功能（删除\)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetRemoveQueryStringConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetRemoveQueryStringConfig|操作接口名，系统规定参数。取值：**SetRemoveQueryStringConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|AliRemoveArgs|String|是|time|删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分。

 |
|KeepOssArgs|String|否|off|取值范围：

 -   **on**：回源保留所有参数
-   **off**：关闭

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetRemoveQueryStringConfig
&DomainName=www.macaron.org.cn
&AliRemoveArgs=time
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>6C59E53D-00F3-4BF3-B8DC-74EC1234BC3D</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"6C59E53D-00F3-4BF3-B8DC-74EC1234BC3D",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The input parameter aliRemoveArgs that is mandatory for processing this request is not supplied.|参数aliRemoveArgs为必填。|
|400|InvalidKeepOssArgs.ValueNotSupported|The specified value of parameter KeepOssArgs is not supported.|KeepOssArgs 不支持该参数值。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

