# 查询域名HTTP返回码占比数据 {#reference_pq4_h5m_vdb .reference}

获取加速域名最小5分钟粒度的HTTP返回码占比数据。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名可用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 请求参数 {#section_gqh_n5m_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainHttpCodeData|系统规定参数。取值：DescribeDomainHttpCodeData|
|DomainName|String|否|test.test.com|需要查询的加速域名，支持批量，多个域名用逗号（半角）分隔。|
|EndTime|String|否|2015-11-30T05:40Z| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300| 查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有运营商。|
|LocationNameEn|String|否|beijing|区域英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有区域。|
|StartTime|String|否|2015-11-30T05:33Z| 获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |
|TimeMerge|String|否|on| 取值范围：

 -   on：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   off：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回参数 {#section_et3_y5m_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|请求ID。|
|DomainName|String|test.test.com|域名。|
|DataInterval|String|300|时间间隔。|
|StartTime|String|2015-11-30T05:33Z|开始时间。|
|EndTime|String|2015-11-30T05:40Z|结束时间。|
|HttpCodeData| | |数据。|
|  └TimeStamp|String|2015-11-30T05:30:00Z|时间戳。|
|  └Value| | |value。|
|    └Code|String|200|http返回码。|
|    └Proportion|String|66.046511627907|占比使用数据。|
|    └Count|String|300|总数。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainHttpCodeData&DomainName="test.com,abc.com"
&StartTime=2015-11-30T05:33Z
&EndTime=2015-11-30T05:40Z
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":"300",
        "DomainName":"test.com,abc.com",
        "EndTime":"2015-11-30T05:40Z",
        "HttpCodeData":{
            "UsageData":[
                {
                    "TimeStamp":"2015-11-30T05:40:00Z",
                    "Value":{
                        "CodeProportionData":[
                            {
                                "Code":"200",
                                "Proportion":"66.046511627907"
                            },
                            {
                                "Code":"206",
                                "Proportion":"4.72868217054264"
                            },
                            {
                                "Code":"302",
                                "Proportion":"0.155038759689922"
                            },
                            {
                                "Code":"304",
                                "Proportion":"0.62015503875969"
                            },
                            {
                                "Code":"500",
                                "Proportion":"28.4496124031008"
                            }
                        ]
                    }
                },
                {
                    "TimeStamp":"2015-11-30T05:35:00Z",
                    "Value":{
                        "CodeProportionData":[
                            {
                                "Code":"200",
                                "Proportion":"64.7822765469824"
                            },
                            {
                                "Code":"206",
                                "Proportion":"3.74331550802139"
                            },
                            {
                                "Code":"302",
                                "Proportion":"0.152788388082506"
                            },
                            {
                                "Code":"304",
                                "Proportion":"1.90985485103132"
                            },
                            {
                                "Code":"500",
                                "Proportion":"29.4117647058824"
                            }
                        ]
                    }
                },
                {
                    "TimeStamp":"2015-11-30T05:30:00Z",
                    "Value":{
                        "CodeProportionData":[
                            {
                                "Code":"200",
                                "Proportion":"67.1458998935037"
                            },
                            {
                                "Code":"206",
                                "Proportion":"12.6730564430245"
                            },
                            {
                                "Code":"302",
                                "Proportion":"0.053248136315229"
                            },
                            {
                                "Code":"304",
                                "Proportion":"0.958466453674121"
                            },
                            {
                                "Code":"500",
                                "Proportion":"19.1693290734824"
                            }
                        ]
                    }
                }
            ]
        },
        "RequestId":"BC858082-736F-4A25-867B-E5B67C85ACF7",
        "StartTime":"2015-11-30T05:33Z"
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


