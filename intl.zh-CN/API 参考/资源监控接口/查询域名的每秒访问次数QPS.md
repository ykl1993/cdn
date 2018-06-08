# 查询域名的每秒访问次数QPS {#reference_an5_gtm_vdb .reference}

获取加速域名的每秒访问次数QPS。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名可用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 请求参数 {#section_b34_ptm_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainQpsData|系统规定参数。取值：DescribeDomainQpsData|
|DomainName|String|否|test.test.com| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|DomainType|String|否|dynamic| 查询类型。

 -   传dynamic时，查询全站加速动态资源的QPS。
-   不传时查询静态资源的QPS。

 |
|EndTime|String|否|2015-12-10T21:00Z| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|FixTimeGap|String|否|false|补零|
|Interval|String|否|300| 查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有运营商。|
|LocationNameEn|String|否|beijing|区域英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有区域。|
|StartTime|String|否|2015-12-10T20:00Z| 获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |
|TimeMerge|String|否|on| 取值范围：

 -   on：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   off：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回参数 {#section_xzj_b5m_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|B8333EDB-4595-46E0-AFE9-29BAA290D0E0|请求ID。|
|DomainName|String|test.test.com| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。|
|StartTime|String|2015-12-10T20:00Z|开始时间。|
|EndTime|String|2015-12-10T21:00Z|结束时间。|
|QpsDataInterval| | |每个时间间隔的每秒访问次数Qps。|
|  └TimeStamp|String|2015-12-10T21:00:00Z|时间片起始时刻。|
|  └Value|String|0|总QPS。|
|  └DomesticValue|String|0|国内QPS。|
|  └OverseasValue|String|0|海外QPS。|
|  └AccValue|String|0|总访问次数。|
|  └AccDomesticValue|String|0|国内访问次数。|
|  └AccOverseasValue|String|0|海外访问次数。|
|  └DynamicValue|String|0|全站加速，动态QPS数据值。|
|  └DynamicDomesticValue|String|0|全站加速，国内带宽动态QPS，当按区域运营商查询时，此值为空。|
|  └DynamicOverseasValue|String|0|全站加速，海外带宽动态QPS，当按区域运营商查询时，此值为空。|
|  └StaticValue|String|0|全站加速，静态QPS数据值。单位：bit/second。|
|  └StaticDomesticValue|String|0|全站加速，国内带宽静态QPS，当按区域运营商查询时，此值为空。|
|  └StaticOverseasValue|String|0|全站加速，海外带宽静态QPS，当按区域运营商查询时，此值为空。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainQpsData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":"300",
        "DomainName":"test.com",
        "EndTime":"2015-12-10T21:00Z",
        "QpsDataInterval":{
            "DataModule":[
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T21:00:00Z",
                    "Value":"0.56"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:35:00Z",
                    "Value":"0.64"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:50:00Z",
                    "Value":"0.4"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"1.0033333333333334"
                }
            ]
        },
        "RequestId":"BEA5625F-8FCF-48F4-851B-CA63946DA664",
        "StartTime":"2015-12-10T20:00Z"
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


