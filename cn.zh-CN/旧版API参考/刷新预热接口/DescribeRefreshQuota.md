# DescribeRefreshQuota {#doc_api_Cdn_DescribeRefreshQuota .reference}

调用DescribeRefreshQuota接口刷新（包含预热）URL及目录的最大限制数量。

限制条件：刷新预热类接口包含 **RefreshObjectCaches**刷新接口和 **PushObjectCache**预热接口。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshQuota)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRefreshQuota|操作接口名，系统规定参数。取值：**DescribeRefreshQuota**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|42E0554B-80F4-4921-AED6-ACFB22CAAAD0|请求ID

 |
|UrlQuota|String|2000|当天url刷新数量上限

 |
|DirQuota|String|100|当天路径刷新数量上限

 |
|UrlRemain|String|1996|当天剩余url刷新数量

 |
|DirRemain|String|99|当天剩余目录刷新数量

 |
|PreloadQuota|String|500|当天预热数量上限

 |
|PreloadRemain|String|400|当天剩余预热数量

 |
|BlockQuota|String|300|当天封禁上限

 |
|blockRemain|String|200|当天封禁剩余量

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeRefreshQuota
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <DirQuota>100</DirQuota>
  <PreloadRemain>500</PreloadRemain>
  <DirRemain>100</DirRemain>
  <blockRemain>100</blockRemain>
  <RequestId>50864C55-AB07-4FA7-AAE8-2F845CFB0278</RequestId>
  <UrlQuota>2000</UrlQuota>
  <UrlRemain>2000</UrlRemain>
  <BlockQuota>100</BlockQuota>
  <PreloadQuota>500</PreloadQuota>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DirQuota":"100",
	"PreloadRemain":"500",
	"DirRemain":"100",
	"blockRemain":"100",
	"RequestId":"50864C55-AB07-4FA7-AAE8-2F845CFB0278",
	"UrlQuota":"2000",
	"UrlRemain":"2000",
	"PreloadQuota":"500",
	"BlockQuota":"100"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

