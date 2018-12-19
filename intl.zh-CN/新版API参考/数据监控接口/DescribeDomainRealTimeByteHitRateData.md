# DescribeDomainRealTimeByteHitRateData {#reference1684 .reference}

获取域名1分钟粒度字节命中率数据。

**说明：** 

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealTimeByteHitRateData|
|DomainName|String|是|域名|
|StartTime|String|否|起始时间。-   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从EndTime起一小时内的数据。

|
|EndTime|String|否|结束时间。-   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从StartTime起一小时内的数据。

|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求Id|
|TimeStamp|String|数据时间戳。-   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

|
|ByteHitRate|Float|字节命中率数据|

## 错误码 { .section}

|错误码|错误信息|HTTP 返回码|描述|
|---|----|--------|--|
|InvalidTime.Malformed|时间参数格式不正确|400|时间参数不正确|
|InvalidDomainName.Malformed|域名参数未提供或找不到域名|400|域名参数不正确|

## 示例 { .section}

请求示例

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeByteHitRateData&DomainName=example.com&EndTime=2018-01-02T11%3A05%3A37Z<公共请求参数>
```

返回示例

```language-json
{
   "Data":{
      "ByteHitRateModel":[
         {
            "TimeStamp":"2018-01-02T11:26:00Z",
            "ByteHitRate":0.8956940476262277
         },
         {
            "TimeStamp":"2018-01-02T11:25:00Z",
            "ByteHitRate":0.8429129920796812
         }
      ]
   },
   "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
}

```

