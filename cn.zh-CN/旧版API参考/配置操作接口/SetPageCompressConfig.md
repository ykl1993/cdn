# SetPageCompressConfig {#doc_api_Cdn_SetPageCompressConfig .reference}

调用SetPageCompressConfig接口设置智能压缩功能。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetPageCompressConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetPageCompressConfig|操作接口名，系统规定参数。取值：**SetPageCompressConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|要设置智能压缩功能的加速域名。

 |
|Enable|String|是|On|是否配置智能压缩功能。取值：

 -   **On**
-   **Off**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetPageCompressConfig
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
  <RequestId>9030E656-29F9-4DF2-A685-740019F6D662</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>MissingEnable</Code>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Recommend":"https://error-center.aliyun.com/status/search?Keyword=MissingEnable&source=PopGw",
	"Message":"Enable is mandatory for this action.",
	"RequestId":"9030E656-29F9-4DF2-A685-740019F6D662",
	"HostId":"cdn.aliyuncs.com",
	"Code":"MissingEnable"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidEnable.ValueNotSupported|The specified value of parameter Enable is not supported.|指定的配置项值不合法，只能是on或off。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

