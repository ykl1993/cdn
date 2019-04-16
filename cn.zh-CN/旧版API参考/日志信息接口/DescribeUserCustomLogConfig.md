# DescribeUserCustomLogConfig {#doc_api_1013123 .reference}

调用DescribeUserCustomLogConfig接口获取用户下所有自定义日志配置信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeUserCustomLogConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserCustomLogConfig|操作接口名，系统规定参数，取值：**DescribeUserCustomLogConfig**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigIds| |\[ "c3bb2c78-2915-4d5a-b6a1-557789255555", "25473b84-d598-498e-b148-f23d0a255555", "1f1e6c6e-6701-4193-ae4d-54bf3e555555" \]|日志配置id

 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求id

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>95D5B69F-8AEC-419B-8F3A-612B35032B0D</RequestId>
  <ConfigIds>
    <ConfigId>c3bb2c78-2915-4d5a-b6a1-557789255555</ConfigId>
    <ConfigId>25473b84-d598-498e-b148-f23d0a255555</ConfigId>
    <ConfigId>1f1e6c6e-6701-4193-ae4d-54bf3e555555</ConfigId>
  </ConfigIds>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"95D5B69F-8AEC-419B-8F3A-612B35032B0D",
	"ConfigIds":{
		"ConfigId":[
			"c3bb2c78-2915-4d5a-b6a1-557789255555",
			"25473b84-d598-498e-b148-f23d0a255555",
			"1f1e6c6e-6701-4193-ae4d-54bf3e555555"
		]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

