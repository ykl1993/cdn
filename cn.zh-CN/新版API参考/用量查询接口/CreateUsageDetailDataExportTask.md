# CreateUsageDetailDataExportTask {#reference2433 .reference}

创建您账户下单个或多个域名5分钟明细数据的导出任务，生成用于下载的excel文件。

**说明：** 该功能从2018年7月20日开始，最长可创建查询近1年数据的任务，单次导出任务跨度最长为1个月。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：CreateUsageDetailDataExportTask。|
|StartTime|String|是|获取数据起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ|
|EndTime|String|是|结束时间需大于起始时间；获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。|
|Group|String|否|域名组信息, 若提供该信息，则忽略DomainNames字段。|
|DomainNames|String|否| -   若域名组为空，则以该字段提供的域名为准导出数据。
-   若该字段未提供, 则导出用户维度数据。

 |
|Type|String|是|需要获取的用量类型：flow或vas。|
|TaskName|String|否|任务名称。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|TaskId|String|任务ID。|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=CreateUsageDetailDataExportTask&Type=flow
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>


```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open Cdn service yet.|403|未开通Cdn服务。|
|OperationDenied|Your Cdn service is suspended.|403|Cdn服务已被停止。|
|InvalidParameter|Invalid Parameter.|400|参数错误。|
|InvalidParameterProduct|Invalid Parameter Product.|400|Product参数错误。|
|InvalidParameterDimension|Invalid Parameter Dimension.|400|Dimension参数错误。|
|InvalidParameterBillType|Invalid Parameter BillType.|400|BillType参数错误。|
|InvalidParameterAliuid|Invalid Parameter Aliuid.|400|Aliuid参数错误。|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|StartTime参数错误。|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|EndTime参数错误。|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|EndTime和StartTime差值不能超过31天。|
|InvalidParameterOperator|Invalid Parameter Operator.|400|Operator参数错误。|

