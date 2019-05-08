# DescribeDomainTopUrlVisit {#doc_api_Cdn_DescribeDomainTopUrlVisit .reference}

调用DescribeDomainTopUrlVisit接口获取加速域名某天内的热门URL列表。

-   不指定**StartTime**，默认读取前一天的数据。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopUrlVisit)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainTopUrlVisit|操作接口名，系统规定参数。取值：**DescribeDomainTopUrlVisit**。

 |
|DomainName|String|否|test.test.com|只支持一个域名，若参数为空，默认返回所有加速域名合并后数据 。

 |
|SortBy|String|否|pv|排序方式。

 -   支持**traf**和**pv**。
-   默认值：**pv**。

 |
|StartTime|String|否|2015-12-03|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AllUrlList| | |全部热门URLlist

 |
|└Flow|String|460486880|流量。单位：byte

 |
|└FlowProportion|Float|0.35|流量占比

 |
|└UrlDetail|String|http://test.com/nn\_live/nn\_x64/a0.m3u8|完整的Url地址

 |
|└VisitData|String|161673|访问次数

 |
|└VisitProportion|Float|0.35|访问占比

 |
|DomainName|String|test.com|加速域名

 |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID

 |
|StartTime|String|2015-12-03|查询指定日期

 |
|Url200List| | |返回为2xx的Urllist

 |
|└Flow|String|460486880|流量。单位：byte。

 |
|└FlowProportion|Float|0.35|流量占比

 |
|└UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址

 |
|└VisitData|String|161673|访问次数

 |
|└VisitProportion|Float|0.35|访问占比

 |
|Url300List| | |返回为3xx的Urllist

 |
|└Flow|String|460486880|流量。单位：byte。

 |
|└FlowProportion|Float|0.35|流量占比

 |
|└UrlDetail|String|http://test.com/nn\_live/nn\_x64/a0.m3u8|完整的Url地址

 |
|└VisitData|String|161673|次数

 |
|└VisitProportion|Float|0.35|访问占比

 |
|Url400List| | |返回为4xx的Urllist

 |
|└Flow|String|460486880|流量。单位：byte。

 |
|└FlowProportion|Float|0.35|流量占比

 |
|└UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址

 |
|└VisitData|String|1884|次数

 |
|└VisitProportion|Float|0.35|访问占比

 |
|Url500List| | |返回为5xx的Urllist

 |
|└Flow|String|460486880|流量。单位：byte。

 |
|└FlowProportion|Float|0.35|流量占比

 |
|└UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址

 |
|└VisitData|String|161673|次数

 |
|└VisitProportion|Float|0.35|访问占比

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>3C7D07F5-44D2-474A-8365-B08FAF439E25</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.ValueNotSupported</Code>
  <Message>The specified value of parameter StartTime is not supported.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The specified value of parameter StartTime is not supported.",
	"RequestId":"3C7D07F5-44D2-474A-8365-B08FAF439E25",
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

