# SetDynamicConfig {#doc_api_Cdn_SetDynamicConfig .reference}

调用SetDynamicConfig接口配置全站加速缓存规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetDynamicConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetDynamicConfig|操作接口名，系统规定参数。取值：**SetDynamicConfig**。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|DynamicCacheControl|String|否|no-cache|特殊header头设置。

 -   根据Header中的Cache-Control字段，选择是否动态加速。多个空格隔开。
-   例如：no-cache no-store private

 |
|DynamicOrigin|String|否|http|回源路由scheme。支持：

 -   **http**
-   **https**
-   **follow**

 不填时，默认值为**http**。

 |
|StaticPath|String|否|/img|静态加速PATH，多个空格隔开。

 例如：\#path:/path/to/no\_dynamic\_route/.\*.one

 |
|StaticType|String|否|jpg|静态加速文件后缀。例如： .\*.\(jpg¦htmp¦txt\)$

 |
|StaticUri|String|否|/img/a.jpg|静态加速URI，多个空格隔开。

 例如：\#uri:/yyy/gggsssssssss/cxxxxxcc/a.txt

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetDynamicConfig
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingDomainName|The input parameter DomainName that is mandatory for processing this request is not supplied.|参数DomainName为必填。|
|400|MissingConfigValue|The input parameter ConfigValue that is mandatory for processing this request is not supplied.|参数ConfigValue为必填。|
|400|InvalidDynamicOrigin.ValueNotSupported|The specified value of parameter DynamicOrigin is not supported.|不支持参数DynamicOrigin。|
|400|InvalidDomainType.ValueNotSupported|The domain is not dynamic domain.|该域名不是动态域名。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

