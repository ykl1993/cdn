# SetIpAllowListConfig {#doc_api_Cdn_SetIpAllowListConfig .reference}

调用SetIpAllowListConfig接口设置加速域名的IP白名单。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetIpAllowListConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetIpAllowListConfig|操作接口名，系统规定参数。取值：**SetIpAllowListConfig**。

 |
|AllowIps|String|是|10.0.0.1%2F24%2C127.0.0.1%2F24|IP白名单。表示此IP列表不受限制，可以正常访问。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|1C2C0CF5-C259-4B1B-98E1-E70DAC3827FA|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetIpAllowListConfig
&AllowIps=10.0.0.1%2F24%2C127.0.0.1%2F24
&DomainName=www.macaron.org.cn
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>1C2C0CF5-C259-4B1B-98E1-E70DAC3827FA</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"1C2C0CF5-C259-4B1B-98E1-E70DAC3827FA",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

