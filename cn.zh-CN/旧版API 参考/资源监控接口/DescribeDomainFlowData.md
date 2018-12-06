# DescribeDomainFlowData {#reference_fqg_5tl_vdb .reference}

获取加速域名的网络流量监控数据，单位：byte。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 请求参数 {#section_ukl_d5l_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainFlowData|系统规定参数。取值：DescribeDomainFlowData|
|DomainName|String|否|www.yourdomain.com| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|DomainType|String|否|dynamic| 查询类型。

 -   传dynamic时，查询全站加速动态资源的实时流量和静态资源的实时流量。
-   不传时查询静态资源的实时流量。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|FixTimeGap|String|否|false|是否补零。|
|Interval|String|否|300| -   查询数据的时间粒度。
-   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有运营商。|
|LocationNameEn|String|否|beijing|区域英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有区域。|
|StartTime|String|否|2017-12-21T08:00:00:00Z| 获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |
|TimeMerge|String|否|on| 取值范围：

 -   on：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   off：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回参数 {#section_h5x_g5l_vdb .section}

|参数|类型|示例值|描述|
|DomainName|String|test.com|加速域名信息。|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。|
|StartTime|String|2015-12-10T20:00Z|开始时间。|
|EndTime|String|2015-12-10T21:00Z|结束时间。|
|FlowDataPerInterval| | |每个时间间隔的流量数据。|
|  └TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻。|
|  └Value|String|423304182|总流量。|
|  └DomesticValue|String|0|国内流量。|
|  └OverseasValue|String|0|海外流量。|
|  └DynamicValue|String|0|全站加速，动态流量，当按区域运营商查询时，此值为空。|
|  └DynamicDomesticValue|String|0|全站加速，国内动态流量，当按区域运营商查询时，此值为空。|
|  └DynamicOverseasValue|String|0|全站加速，海外动态流量，当按区域运营商查询时，此值为空。|
|  └StaticValue|String|0|全站加速，静态流量，当按区域运营商查询时，此值为空。|
|  └StaticDomesticValue|String|0|全站加速，国内静态流量，当按区域运营商查询时，此值为空。|
|  └StaticOverseasValue|String|0|全站加速，海外静态流量，当按区域运营商查询时，此值为空。|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainFlowData&DomainName=test.com
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
        "FlowDataPerInterval":{
            "DataModule":[
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"423304182"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"454680793"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:10:00Z",
                    "Value":"501718342"
                },
                {
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:15:00Z",
                    "Value":"434816025"
                }
            ]
        },
        "RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E",
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


