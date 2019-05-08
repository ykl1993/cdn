# SetUserGreenManagerConfig {#doc_api_Cdn_SetUserGreenManagerConfig .reference}

调用SetUserGreenManagerConfig接口设置用户的图片鉴黄配置，包括抽检比例和限额。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetUserGreenManagerConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetUserGreenManagerConfig|操作接口名，系统规定参数。取值：**SetUserGreenManagerConfig**。

 |
|Quota|String|是|xxx|图片鉴黄功能的限额，取值不少于10万。

 |
|Ratio|String|是|xxx|图片鉴黄功能的抽检比例。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetUserGreenManagerConfig
&Quota=xxx
&Ratio=xxx
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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

