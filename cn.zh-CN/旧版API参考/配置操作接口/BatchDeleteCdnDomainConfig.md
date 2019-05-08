# BatchDeleteCdnDomainConfig {#doc_api_Cdn_BatchDeleteCdnDomainConfig .reference}

调用BatchDeleteCdnDomainConfig接口删除域名配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=BatchDeleteCdnDomainConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchDeleteCdnDomainConfig|操作接口名，系统规定参数。取值：**BatchDeleteCdnDomainConfig**。

 |
|DomainNames|String|是|www.macaron.org.cn,xxx.org.com|您的加速域名，多个用英文半角逗号分隔。

 |
|FunctionNames|String|是|referer\_white\_list\_set,https\_force|功能列表名称，用逗号分隔。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=BatchDeleteCdnDomainConfig
&DomainNames=www.macaron.org.cn,xxx.org.com
&FunctionNames=referer_white_list_set,https_force
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>4F001F79-F67A-43DF-B512-BB4DFB7109FB</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"4F001F79-F67A-43DF-B512-BB4DFB7109FB",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|此方法不支持。|
|400|DeleteFunctionFailed|Batch delete functions failed.|批量删除功能失败。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

