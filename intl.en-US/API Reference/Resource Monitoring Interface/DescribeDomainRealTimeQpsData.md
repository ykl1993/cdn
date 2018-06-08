# DescribeDomainRealTimeQpsData {#reference_jy2_sqs_vdb .reference}

Obtain access times data per second of the domain name with 1-minute granularity.

-   Data query from the past 7 days is supported, but the time interval between the StartTime and EndTime for a single query does not exceed 24 hours.
-   When StartTime and EndTime are not specified, the system reads data from the past 1 hour by default.

## Request parameters {#section_nml_kxs_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainRealTimeQpsData|The name of this interface. Value: DescribeDomainRealTimeQpsData|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If the parameter is left blank, the data of 1 hour from EndTime is read by default.

 |
|IspNameEn|String|No|telecom|ISP name in English, obtained by using the DescribeCdnRegionAndIsp interface. If ths parameter is left blank, the English names of all carriers are obtained.|
|LocationNameEn|String|No|beijing|Region name in English, obtained by using the DescribeCdnRegionAndIspinterface. If the parameter is left blank, the English names of all regions are obtained.|
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If this parameter is unspecified, data of 1 hour from EndTime is read by default.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_nfh_kys_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D|The ID of the request.|
|Data| | |Returns data.|
| └Qps|Float|1851.25|qps data.|
|  └TimeStamp|String|2018-01-02T11:26:00Z| The time stamp.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeQpsData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Z&IspNameEn=telecom&LocationNameEn=beijingPublic request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Data ":{
            "QpsModel":[
                
                    "Qps":1851.25,
                    "TimeStamp":"2018-01-02T11:26:00Z"
                
                
                    "Qps":8967.7,
                    "TimeStamp":"2018-01-02T11:25:00Z"
                
            
        
        "RequestId":"32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


