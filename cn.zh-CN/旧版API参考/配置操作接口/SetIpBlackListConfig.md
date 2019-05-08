# SetIpBlackListConfig {#doc_api_Cdn_SetIpBlackListConfig .reference}

调用SetIpBlackListConfig接口设置加速域名的IP黑名单。

**说明：** IP黑名单当前支持IP网段添加。例如：127.0.0.1/24 24表示采用子网掩码中的前24位为有效位，即用32-24 = 8 bit来表示主机号，该子网可以容纳2^8-2 = 254 台主机。故127.0.0.1/24 表示的IP网段范围是：127.0.0.1~127.0.0.255。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetIpBlackListConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetIpBlackListConfig|操作接口名，系统规定参数。取值：**SetIpBlackListConfig**。

 |
|BlockIps|String|是|192.168.0.1|IP黑名单。表示此IP列表禁止访问，IP列表多个用逗号隔开。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetIpBlackListConfig
&BlockIps=192.168.0.1
&DomainName=www.macaron.org.cn
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>E69AA279-C6BF-41D3-814B-B54FD2E3C0F8</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"E69AA279-C6BF-41D3-814B-B54FD2E3C0F8",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

