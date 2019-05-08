# DescribeDomainTopReferVisit {#doc_api_Cdn_DescribeDomainTopReferVisit .reference}

调用DescribeDomainTopReferVisit接口获取加速域名某天的热门页面引用次数排名。

-   不指定**StartTime**，默认读取前一天的数据。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopReferVisit)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainTopReferVisit|操作接口名，系统规定参数。取值：**DescribeDomainTopReferVisit**。

 |
|DomainName|String|否|www.yourdomain.com|只支持一个域名，若参数为空，默认返回所有加速域名合并后数据。

 |
|SortBy|String|否|pv|排序方式。

 -   支持**traf**和**pv**。
-   默认值：**pv**。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|95994621-8382-464B-8762-C708E73568D1|请求ID

 |
|DomainName|String|test.com|加速域名信息

 |
|StartTime|String|2015-11-28|查询指定日期

 |
|TopReferList| | |全部热门ReferUrllist

 |
|└ReferDetail|String|live-hunantv.cdnpe.com|完整的ReferUrl地址

 |
|└VisitData|String|3|访问次数

 |
|└Flow|String|200|流量。单位：byte。

 |
|└FlowProportion|Float|0.5|流量占比

 |
|└VisitProportion|Float|0.5|访问占比

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainTopReferVisit
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>BB7791EF-CEA4-4A45-90FC-6A7B66A57D50</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.ValueNotSupported</Code>
  <Message>The specified value of parameter StartTime is not supported.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The specified value of parameter StartTime is not supported.",
	"RequestId":"BB7791EF-CEA4-4A45-90FC-6A7B66A57D50",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidStartTime.ValueNotSupported"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter "StartTime" is not valid.|参数“StartTime”的值无效。|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|参数DomainName可以为空或最多1个域名。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

