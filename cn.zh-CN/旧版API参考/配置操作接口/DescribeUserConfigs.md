# DescribeUserConfigs {#doc_api_Cdn_DescribeUserConfigs .reference}

调用DescribeUserConfigs接口获取用户相应的配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeUserConfigs)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserConfigs|操作接口名，系统规定参数。取值：**DescribeUserConfigs**。

 |
|Config|String|是|oss|需要查询的配置，支持单个查询。取值：

 -   **oss**
-   **green\_manager**
-   **waf**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Configs| | |对应的配置数据

 |
|└GreenManagerConfig| | |图片鉴黄功能配置

 |
|└OssLogConfig| | |oss日志存储配置

 |
|└WafConfig| | |waf功能配置

 |
|RequestId|String|9BCC7BAA-ACBE-45E5-83F0-98BF7E693E84|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeUserConfigs
&Config=123
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>85532302-EB9D-42E4-ACB4-DDD735722998</RequestId>
  <Configs>
    <OssLogConfig/>
    <WafConfig/>
    <GreenManagerConfig/>
  </Configs>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"85532302-EB9D-42E4-ACB4-DDD735722998",
	"Configs":{
		"OssLogConfig":{},
		"WafConfig":{},
		"GreenManagerConfig":{}
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingConfig|The input parameter Config that is mandatory for processing this request is not supplied.|参数Config为必填。|
|400|InvalidConfig.ValueNotSupported|The specified value of parameter "Config" is not supported.|参数“Config”的值无效。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

