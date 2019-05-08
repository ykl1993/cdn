# ModifyFileCacheExpiredConfig {#doc_api_Cdn_ModifyFileCacheExpiredConfig .reference}

调用ModifyFileCacheExpiredConfig接口修改文件过期配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=ModifyFileCacheExpiredConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyFileCacheExpiredConfig|操作接口名，系统规定参数。取值：**ModifyFileCacheExpiredConfig**。

 |
|CacheContent|String|是|jpg,png|填写文件名后缀，逗号分隔。

 |
|ConfigID|String|是|905535|要修改的配置ID。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|TTL|String|是|600|缓存时间设置。单位：秒。

 |
|Weight|String|否|22|该配置权重值。

 取值范围：1~99。数值越大，优先级越高。

 默认值：1。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=ModifyFileCacheExpiredConfig
&CacheContent=jpg,png
&ConfigID=905535
&DomainName=www.yourdomain.com
&TTL=600
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>73F1BF89-C14A-4B06-8166-4C73F63D4425</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"73F1BF89-C14A-4B06-8166-4C73F63D4425",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidWeight.Malformed|The specified value of parameter Weight is malformed.|指定的权重值不合法，格式错误。|
|400|InvalidWeight.ValueNotSupported|The specified value of parameter Weight is not supported.|指定的权重值不合法，超出可选范围。|
|400|InvalidConfigID.NotFound|Cannot find the specific value of parameter ConfigID in our system.|找不到ConfigID。|
|400|InvalidConfigID.Malformed|The specific value of parameter ConfigID is malformed.|参数ConfigID格式错误。|
|404|ConfigNotFound|Config not found|您输入的configid不存在，或输入的域名和configid不匹配，请检查更新后重试。|
|400|InvalidTTL.Malformed|The specified value of parameter TTL is malformed.|参数TTL的参数格式错误，请检查更新后重试。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

