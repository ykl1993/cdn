# DescribeTopDomainsByFlow {#reference_zlg_qwm_vdb .reference}

获取用户按流量排名的域名。

-   不指定StartTime和EndTime时，默认读取当月的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   最多可获取最近90天的数据。

## 请求参数 {#section_oth_xwm_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeTopDomainsByFlow|系统规定参数。取值：DescribeTopDomainsByFlow|
|EndTime|String|否|2017-12-22T08:00:00:00Z| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Limit|Long|否|20| 域名获取数量限制。

 取值范围：1~100

 默认值：20

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z| -   获取数据起始时间点。
-   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取当月数据。

 |

## 返回参数 {#section_yhh_dxm_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70|请求ID。|
|StartTime|String|2016-03-01T04:00Z|开始时间。|
|EndTime|String|2016-03-14T07:34Z|结束时间。|
|TopDomains| | |排名域名列表。|
|  └DomainName|String|test.test.com|域名。|
|  └Rank|Long|1|排名。|
|  └TotalTraffic|String|2043859876683.9001|总流量。|
|  └TrafficPercent|String|30.64191989360235|流量占比。|
|  └MaxBps|Long|22139626|带宽峰值。|
|  └MaxBpsTime|String|1457111400|带宽峰值时刻。|
|  └TotalAccess|Long|107784230|访问次数。|
|DomainCount|Long|68|账户下域名总数。|
|DomainOnlineCount|Long|68|账户下正在运行”域名总数。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&StartTime=2015-11-29
&EndTime=2015-11-30
&Limit=5
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DomainCount":68,
        "DomainOnlineCount":68,
        "EndTime":"2016-03-14T07:34Z",
        "RequestId":"4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70",
        "StartTime":"2016-03-01T04:00Z",
        "TopDomains":{
            "TopDomain":[
                {
                    "DomainName":"cedexis.j0zz.com",
                    "MaxBps":22139626,
                    "MaxBpsTime":1457111400,
                    "Rank":1,
                    "TotalAccess":107784230,
                    "TotalTraffic":2043859876683.9001,
                    "TrafficPercent":30.64191989360235
                },
                {
                    "DomainName":"wj.cdnpe.com",
                    "MaxBps":1008772351,
                    "MaxBpsTime":1457505600,
                    "Rank":2,
                    "TotalAccess":3843128,
                    "TotalTraffic":1729970466149.2002,
                    "TrafficPercent":25.936032624725815
                },
                {
                    "DomainName":"imgtest.cdnpe.com",
                    "MaxBps":16046911,
                    "MaxBpsTime":1456897200,
                    "Rank":3,
                    "TotalAccess":547567,
                    "TotalTraffic":1446507574551.6,
                    "TrafficPercent":21.686305274906182
                },
                {
                    "DomainName":"downtest.cdnpe.com",
                    "MaxBps":15990893,
                    "MaxBpsTime":1457567700,
                    "Rank":4,
                    "TotalAccess":548380,
                    "TotalTraffic":1418144519687.5,
                    "TrafficPercent":21.261081185428147
                },
                {
                    "DomainName":"ali.ddimg.cn",
                    "MaxBps":473599,
                    "MaxBpsTime":1457845800,
                    "Rank":5,
                    "TotalAccess":152150,
                    "TotalTraffic":28739937242.500004,
                    "TrafficPercent":0.4308743788055894
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


