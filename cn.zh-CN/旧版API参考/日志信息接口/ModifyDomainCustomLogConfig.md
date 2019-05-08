# ModifyDomainCustomLogConfig {#doc_api_Cdn_ModifyDomainCustomLogConfig .reference}

调用ModifyDomainCustomLogConfig接口修改域名所属日志自定义日志配置信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=ModifyDomainCustomLogConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDomainCustomLogConfig|操作接口名，系统规定参数，取值：**ModifyDomainCustomLogConfig**。

 |
|ConfigId|String|是|123|日志配置ID

 |
|DomainName|String|是|a.com|域名

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求id

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?ConfigId=123
&DomainName=a.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>649E6A1C-513E-431A-83BC-81E750A8476D</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"649E6A1C-513E-431A-83BC-81E750A8476D",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

