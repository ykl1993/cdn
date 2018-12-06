# DescribeDomainUvData {#reference_ubn_cym_vdb .reference}

获取加速域名最小1小时粒度的 UV页面独立访问统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 请求参数 {#section_oth_3ym_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainUvData|系统规定参数。取值：DescribeDomainUvData|
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|EndTime|String|否|2015-11-29| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|StartTime|String|否|2015-11-29| 获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#section_j5s_nym_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|E9D3257A-1B7C-414C-90C1-8D07AC47BCAC|请求ID。|
|DomainName|String|ttest.test.com|查询的加速域名。|
|DataInterval|String|3600|时间间隔。|
|StartTime|String|2015-11-30|获取数据起始时间点。|
|EndTime|String|2015-11-30|获取数据结束时间点。|
|UvDataInterval| | |数据。|
|  └TimeStamp|String|2015-11-29T20:00:00Z|时间戳。|
|  └Value|String|318|UV。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainUvData&DomainName=test.com
&StartTime=2015-11-29
&EndTime=2015-11-30
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":"3600",
        "DomainName":"test.com",
        "EndTime":"2015-11-30",
        "RequestId":"E9D3257A-1B7C-414C-90C1-8D07AC47BCAC",
        "StartTime":"2015-11-29",
        "UvDataInterval":{
            "UsageData":[
                {
                    "TimeStamp":"2015-11-29T20:00:00Z",
                    "Value":"318"
                },
                {
                    "TimeStamp":"2015-11-29T18:00:00Z",
                    "Value":"318"
                },
                {
                    "TimeStamp":"2015-11-29T03:00:00Z",
                    "Value":"329"
                },
                {
                    "TimeStamp":"2015-11-29T21:00:00Z",
                    "Value":"316"
                },
                {
                    "TimeStamp":"2015-11-29T07:00:00Z",
                    "Value":"319"
                },
                {
                    "TimeStamp":"2015-11-29T00:00:00Z",
                    "Value":"326"
                },
                {
                    "TimeStamp":"2015-11-29T11:00:00Z",
                    "Value":"321"
                },
                {
                    "TimeStamp":"2015-11-29T10:00:00Z",
                    "Value":"313"
                },
                {
                    "TimeStamp":"2015-11-29T08:00:00Z",
                    "Value":"331"
                },
                {
                    "TimeStamp":"2015-11-29T01:00:00Z",
                    "Value":"324"
                },
                {
                    "TimeStamp":"2015-11-29T04:00:00Z",
                    "Value":"330"
                },
                {
                    "TimeStamp":"2015-11-29T14:00:00Z",
                    "Value":"335"
                },
                {
                    "TimeStamp":"2015-11-29T12:00:00Z",
                    "Value":"318"
                },
                {
                    "TimeStamp":"2015-11-29T23:00:00Z",
                    "Value":"310"
                },
                {
                    "TimeStamp":"2015-11-29T17:00:00Z",
                    "Value":"309"
                },
                {
                    "TimeStamp":"2015-11-29T22:00:00Z",
                    "Value":"320"
                },
                {
                    "TimeStamp":"2015-11-29T16:00:00Z",
                    "Value":"309"
                },
                {
                    "TimeStamp":"2015-11-29T02:00:00Z",
                    "Value":"317"
                },
                {
                    "TimeStamp":"2015-11-29T06:00:00Z",
                    "Value":"309"
                },
                {
                    "TimeStamp":"2015-11-29T19:00:00Z",
                    "Value":"308"
                },
                {
                    "TimeStamp":"2015-11-29T13:00:00Z",
                    "Value":"347"
                },
                {
                    "TimeStamp":"2015-11-29T15:00:00Z",
                    "Value":"341"
                },
                {
                    "TimeStamp":"2015-11-29T05:00:00Z",
                    "Value":"347"
                },
                {
                    "TimeStamp":"2015-11-29T09:00:00Z",
                    "Value":"312"
                }
            ]
        }
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


