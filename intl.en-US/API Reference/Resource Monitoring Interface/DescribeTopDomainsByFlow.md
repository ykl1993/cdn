# DescribeTopDomainsByFlow {#reference_zlg_qwm_vdb .reference}

Obtain the domain names that are ranked by traffic.

-   When you do not specify StartTime and EndTime, the interface reads data from the past month by default. Query by specified start time and end time is also supported. You must specify the two parameters.
-   You can obtain data from the past 90 days at most.

## Request parameters {#section_oth_xwm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeTopDomainsByFlow|The name of this interface. Value: DescribeTopDomainsByFlow|
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|Limit|Long|No|20| Limit on the number of obtained domain names.

 Value range: 1~100 

 Default value: 20

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| -   Start time of data query.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is left blank, the interface reads data from the current month by default.

 |

## Return parameters {#section_yhh_dxm_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70|The ID of the request.|
|StartTime|String|2016-03-01T04:00Z|Start time.|
|EndTime|String|2016-03-14T07:34Z|End time.|
|TopDomains| | |List of ranked domain names.|
|  └DomainName|String|test.test.com|Domain name.|
|  └Rank|Long|1|Ranking.|
|  └TotalTraffic|String|2043859876683.9001|Total flow.|
|  └TrafficPercent|String|30.64191989360235|Traffic proportion.|
|  └MaxBps|Long|22139626|Peak bandwidth.|
|  └MaxBpsTime|String|1457111400|Peak bandwidth time.|
|  └TotalAccess|Long|107784230|Times of access.|
|DomainCount|Long|68.|Total number of domain names under the account.|
|DomainOnlineCount|Long|68.|Total number of running domain names under the account.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&StartTime=2015-11-29
&EndTime=2015-11-30
&Limit=5
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DomainCount":68,
        "DomainOnlineCount":68,
        "EndTime":"2016-03-14T07:34Z",
        "RequestId":"4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70",
        "StartTime":"2016-03-01T04:00Z",
        "TopDomains":{
            "TopDomain":[
                
                    "DomainName":"cedexis.j0zz.com",
                    "MaxBps":22139626,
                    "MaxBpsTime":1457111400,
                    "Rank":1,
                    "TotalAccess":107784230,
                    "TotalTraffic":2043859876683.9001,
                    "TrafficPercent":30.64191989360235
                
                
                    "DomainName":"wj.cdnpe.com",
                    "MaxBps":1008772351,
                    "MaxBpsTime":1457505600,
                    "Rank":2,
                    "TotalAccess":3843128,
                    "TotalTraffic":1729970466149.2002,
                    "TrafficPercent":25.936032624725815
                
                
                    "DomainName":"imgtest.cdnpe.com",
                    "MaxBps":16046911,
                    "MaxBpsTime":1456897200,
                    "Rank":3,
                    "TotalAccess":547567,
                    "TotalTraffic":1446507574551.6,
                    "TrafficPercent":21.686305274906182
                
                
                    "DomainName":"downtest.cdnpe.com",
                    "MaxBps":15990893,
                    "MaxBpsTime":1457567700,
                    "Rank":4,
                    "TotalAccess":548380,
                    "TotalTraffic":1418144519687.5,
                    "TrafficPercent":21.261081185428147
                
                
                    "DomainName":"ali.ddimg.cn",
                    "MaxBps":473599,
                    "MaxBpsTime":1457845800,
                    "Rank":5,
                    "TotalAccess":152150,
                    "TotalTraffic":28739937242.500004,
                    "TrafficPercent":0.4308743788055894
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


