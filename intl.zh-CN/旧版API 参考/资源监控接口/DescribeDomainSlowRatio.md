# DescribeDomainSlowRatio {#reference_qg3_kzs_vdb .reference}

获取视频加速域名5分钟维度的慢速比数据。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   不支持批量域名查询。
-   最多可获取最近30天的数据。

## 请求参数 {#section_mdq_qzs_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainSlowRatio|系统规定参数。取值：DescribeDomainSlowRatio|
|DomainName|String|是|test.test.com|加速域名。|
|EndTime|String|否|2016-10-20T04:00:00Z| 结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   起止时间和结束时间，间隔小于30天。
-   例如：2016-10-20T04:00:00Z。

 |
|PageNumber|Integer|否|1|页号，从1开始。|
|PageSize|Integer|否|20|每页大小。|
|StartTime|String|否|2016-10-20T04:00:00Z| 开始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|Version|String|否|2014-11-11|API版本。|

## 返回参数 {#section_cvq_vzs_vdb .section}

|参数|类型|示例值|描述|
|EndTime|String|017-09-30T16:00:00Z|结束时间。|
|DataInterval|Integer|300| 时间间隔。

 单位：秒

 |
|PageNumber|Integer|1|当前页码，从1开始计数。|
|PageSize|Integer|20|页大小。|
|TotalCount|Integer|2|慢速比数据条数。|
|StartTime|String|017-09-30T16:00:00Z|起始时间。|
|SlowRatioDataPerInterval| | |慢速比数据列表。|
|  └TotalUsers|Integer|15|总用户数。|
|  └SlowUsers|Integer|3|慢速用户数。|
|  └SlowRatio|Float|0.2|慢速比例。|
|  └RegionNameZh|String|北京市|地区中文信息。|
|  └RegionNameEn|String|beijing|地区英文信息。|
|  └IspNameZh|String|联通|运营商中文信息。|
|  └IspNameEn|String|unicom|运营商英文信息。|
|  └Time|String|2017-09-30T16:00:00Z|时间点。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?Action=DescribeDomainSlowRatio&DomainName=&PageNumber=1&PageSize=20
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":300,
        "EndTime":"2017-09-30T17:00:00Z",
        "PageNumber":1,
        "PageSize":20,
        "SlowRatioDataPerInterval":{
            "SlowRatioData":[
                {
                    "IspNameEn":"telecom",
                    "IspNameZh":"电信",
                    "RegionNameEn":"guangdong",
                    "RegionNameZh":"广东省",
                    "SlowRatio":0.1,
                    "SlowUsers":2,
                    "Time":"2017-09-30T16:00:00Z",
                    "TotalUsers":20
                },
                {
                    "IspNameEn":"unicom",
                    "IspNameZh":"联通",
                    "RegionNameEn":"beijing",
                    "RegionNameZh":"北京市",
                    "SlowRatio":0.2,
                    "SlowUsers":3,
                    "Time":"2017-09-30T16:00:00Z",
                    "TotalUsers":15
                }
            ]
        },
        "StartTime":"2017-09-30T16:00:00Z",
        "TotalCount":2
    }
    ```


**异常返回示例**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```


