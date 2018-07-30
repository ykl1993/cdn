# DescribeDomainRealTimeByteHitRateData {#reference_icl_cps_vdb .reference}

Obtain byte hit rate data of domain names with 1-minute granularity.

-   Data from the past 7 days can be queried. The time span between the start time and end time for a single query does not exceed 24 hours.
-   When StartTime and EndTime are not specified, data from the past one hour is returned by default.

**Note:** Because multiple domain names can be stored together, the possibility that the hit rate data is inaccurate exists. In the event of any inaccuracy, the specific configuration prevails.

## Request parameters {#section_yh3_pps_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainRealTimeByteHitRateData|The name of this interface. Value: DescribeDomainRealTimeByteHitRateData|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If this parameter is left blank, data of one hour from StartTime is read by default.

 |
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If this parameter is left blank, data of one hour from the End time is read bu default.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_fcl_5ps_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|The request ID.|
|Data| | |Returned data.|
|  └ByteHitRate|Float|0.8956940476262277|Byte hit rate data.|
|  └TimeStamp|String|2016-10-20T04:00:00Z| The time stamp of data.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |

## Example {#section_uz2_x1n_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeByteHitRateData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Zpublic request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Data":{
            "ByteHitRateModel":[
                
                    "ByteHitRate":0.8956940476262277,
                    "TimeStamp":"2018-01-02T11:26:00Z"
                
                
                    "ByteHitRate":0.8429129920796812,
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


