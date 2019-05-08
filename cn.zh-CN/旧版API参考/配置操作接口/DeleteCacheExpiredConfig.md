# DeleteCacheExpiredConfig {#doc_api_Cdn_DeleteCacheExpiredConfig .reference}

调用DeleteCacheExpiredConfig接口删除自定义缓存策略.。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DeleteCacheExpiredConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteCacheExpiredConfig|操作接口名，系统规定参数。取值：**DeleteCacheExpiredConfig**。

 |
|CacheType|String|是|suffix|缓存内容类型。取值范围：

 -   **suffix**：文件名后缀。
-   **path**：路径，支持目录和完整路径。

 |
|ConfigID|String|是|903423|配置ID。

 -   新增时，不需要指定。
-   修改时，需要指定。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DeleteCacheExpiredConfig
&CacheType=suffix
&ConfigID=903423
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
|400|InvalidCacheType.ValueNotSupported|The specified value of parameter CacheType is not supported.|指定的缓存内容类型不合法，超出可选范围。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

