# ListDomainsByLogConfigId {#doc_api_Cdn_ListDomainsByLogConfigId .reference}

调用ListDomainsByLogConfigId接口查询应用某自定义日志格式的所有域名列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=ListDomainsByLogConfigId)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ListDomainsByLogConfigId|操作接口名，系统规定参数，取值：**ListDomainsByLogConfigId**。

 |
|ConfigId|String|是|123|自定义配置ID

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Domains| |\[ "abc.com", "a.b.c.com" \]|域名列表

 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求id

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?ConfigId=123
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>48370D63-6BB6-462A-B7ED-DEB36077913D</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidConfigId</Code>
  <Message>Illegal ConfigId</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Illegal ConfigId",
	"RequestId":"48370D63-6BB6-462A-B7ED-DEB36077913D",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidConfigId"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

