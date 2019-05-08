# SetForwardSchemeConfig {#doc_api_Cdn_SetForwardSchemeConfig .reference}

调用SetForwardSchemeConfig接口设置回源协议。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetForwardSchemeConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetForwardSchemeConfig|操作接口名，系统规定参数。取值：**SetForwardSchemeConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|Enable|String|是|on|是否开启。

 -   **on**：开启
-   **off**：关闭

 |
|SchemeOrigin|String|是|follow|回源站协议。取值：

 -   **http**
-   **https**
-   **follow**：协议跟随回源

 |
|SchemeOriginPort|String|是|80:443|回源站协议端口。取值：80、443、80:443，与SchemeOrigin一一对应。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|DD6193E9-CC5A-4C08-9207-6B73DF0892BF|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetForwardSchemeConfig
&DomainName=www.macaron.org.cn
&Enable=on
&SchemeOrigin=follow
&SchemeOriginPort=80:443
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <Recommend>https://error-center.aliyun.com/status/search?Keyword=MissingEnable&amp;source=PopGw</Recommend>
  <Message>Enable is mandatory for this action.</Message>
  <RequestId>DD6193E9-CC5A-4C08-9207-6B73DF0892BF</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>MissingEnable</Code>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Recommend":"https://error-center.aliyun.com/status/search?Keyword=MissingEnable&source=PopGw",
	"Message":"Enable is mandatory for this action.",
	"RequestId":"DD6193E9-CC5A-4C08-9207-6B73DF0892BF",
	"HostId":"cdn.aliyuncs.com",
	"Code":"MissingEnable"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidEnable.ValueNotSupported|The specified value of parameter Enable is not supported.|指定的配置项值不合法，只能是on或off。|
|400|InvalidSchemeOrigin.ValueNotSupported|The specified value of parameter SchemeOrigin is not supported.|不支持参数SchemeOrigin。|
|400|InvalidSchemeOriginPort.ValueNotSupported|The specified value of parameter SchemeOriginPort is not supported.|不支持参数SchemeOriginPort 。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

