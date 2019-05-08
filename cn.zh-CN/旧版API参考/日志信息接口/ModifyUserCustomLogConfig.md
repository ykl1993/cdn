# ModifyUserCustomLogConfig {#doc_api_Cdn_ModifyUserCustomLogConfig .reference}

调用ModifyUserCustomLogConfig接口修改用户下自定义日志配置信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=ModifyUserCustomLogConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyUserCustomLogConfig|操作接口名，系统规定参数，取值：**ModifyUserCustomLogConfig**。

 |
|ConfigId|String|是|1232|日志配置ID

 |
|Tag|String|是|music|日志配置tag信息\(不超过256个字符\)

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求id

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?ConfigId=1232
&Tag=music
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>86EE14A7-63EE-460D-9D2A-5C88536859A8</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidConfigId</Code>
  <Message>The configId does not exist.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The configId does not exist.",
	"RequestId":"86EE14A7-63EE-460D-9D2A-5C88536859A8",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidConfigId"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

