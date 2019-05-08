# SetIgnoreQueryStringConfig {#doc_api_Cdn_SetIgnoreQueryStringConfig .reference}

调用SetIgnoreQueryStringConfig接口设置过滤参数功能。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetIgnoreQueryStringConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetIgnoreQueryStringConfig|操作接口名，系统规定参数。取值：**SetIgnoreQueryStringConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|要开启该功能的加速域名。

 |
|Enable|String|是|On|是否配置过滤参数功能。取值：

 -   **On**
-   **Off**

 |
|HashKeyArgs|String|否|time|保留参数。多个用逗号（英文、半角）分隔，最多配置10个保留参数。

 |
|KeepOssArgs|String|否|on|取值：

 -   **On**：回源保留所有参数
-   **Off**：关闭

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetIgnoreQueryStringConfig
&DomainName=www.macaron.org.cn
&Enable=On
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <Recommend>https://error-center.aliyun.com/status/search?Keyword=MissingEnable&amp;source=PopGw</Recommend>
  <Message>Enable is mandatory for this action.</Message>
  <RequestId>0067CC21-D05C-4854-8B85-99BC60BA5EF8</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>MissingEnable</Code>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Recommend":"https://error-center.aliyun.com/status/search?Keyword=MissingEnable&source=PopGw",
	"Message":"Enable is mandatory for this action.",
	"RequestId":"0067CC21-D05C-4854-8B85-99BC60BA5EF8",
	"HostId":"cdn.aliyuncs.com",
	"Code":"MissingEnable"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidEnable.ValueNotSupported|The specified value of parameter Enable is not supported.|指定的配置项值不合法，只能是on或off。|
|400|InvalidHashKeyArgs.ValueNotSupported|At most 10 HashKeyArgs are supported.|最多配置10个保留参数。|
|400|InvalidKeepOssArgs.ValueNotSupported|The specified value of parameter KeepOssArgs is not supported.|KeepOssArgs 不支持该参数值。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

