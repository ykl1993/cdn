# DescribeDomainCustomLogConfig {#doc_api_Cdn_DescribeDomainCustomLogConfig .reference}

调用DescribeDomainCustomLogConfig接口获取域名自定义日志格式配置信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainCustomLogConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainCustomLogConfig|操作接口名，系统规定参数，取值：**DescribeDomainCustomLogConfig**。

 |
|DomainName|String|是|www.yourdomain.com|域名（只支持单个查询）。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigId|String|123|日志配置id

 |
|Remark|String|$time\_iso8601\_$request\_method\_$|具体配置格式

 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求id

 |
|Sample|String|\[9/Jun/2015:01:58:09+0800\]188.165.15.75-1542\\"-\\"\\"GET http://www.aliyun.com/index.html\\|样例

 |
|Tag|String|book|日志配置tag信息

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>291ECC42-75B0-4B6C-B8C8-489400203B48</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"291ECC42-75B0-4B6C-B8C8-489400203B48",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

