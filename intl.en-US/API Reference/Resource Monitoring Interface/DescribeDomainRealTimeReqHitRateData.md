# DescribeDomainRealTimeReqHitRateData {#reference_qll_rys_vdb .reference}

Obtain the request hit rate of the domain name with 1-minute granularity.

-   Data query from the past 7 days is supported, but the time interval between StartTime and EndTime for a single query does not exceed 24 hours.
-   When StartTime and EndTime are not specified, the system reads data from the past one hour by default.

**Note:** Because multiple domain names can be stored together, the possibility that the hit rate data is not accturate exists. In case of any inaccuracy, the specific configuration prevails.

## Request parameters {#section_wz2_yys_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainRealTimeReqHitRateData|The name of this interface. Value: DescribeDomainRealTimeReqHitRateData|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_ggn_2zs_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|The ID of the request.|
|Data| | |Returned data.|
|  └ReqHitRate|Float|0.8956940476262277|Request hit rate data.|
|  └TimeStamp|String|2018-01-02T11:25:00Z| Time stamp.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeReqHitRateData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37ZPublic request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Data":{
            "ReqHitRateModel":[
                
                    "ReqHitRate":0.8956940476262277,
                    "TimeStamp":"2018-01-02T11:26:00Z"
                
                
                    "ReqHitRate":0.8429129920796812,
                    "TimeStamp":"2018-01-02T11:25:00Z"
                
            
        
        "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


