# DescribeDomainRealTimeBpsData {#reference_aqm_kns_vdb .reference}

Obtain bandwidth data of domain name with 1-minute granularity.

-   Data query from the past 7 days is supported, but the time interval between the StartTime and EndTime for a single query does not exceed 24 hours.
-   When StartTime and EndTime are not specified, the system reads data from the past one hour by default.

## Request parameters {#section_ngq_qns_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainRealTimeBpsData|The name of this interface.  Value: DescribeDomainRealTimeBpsData|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If this parameter is left blank, data of one hour from StartTime is queried by default.

 |
|IspNameEn|String|No|telecom|ISP names in English, obtained by using DescribeCdnRegionAndIsp interface. If this parametr is left blank, the system reads all the ISP names by default.|
|LocationNameEn|String|No|beijing|Region name in English, obtained by using DescribeCdnRegionAndIsp interface. If this parameter is left blank, the system reads all the region names by default.|
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.
-   If this parameter is left blank, data of one hour from EndTime is queried by default.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_btb_tns_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|B49E6DDA-F413-422B-B58E-2FA23F286726|The ID of the request.|
|Data| | |Returned data.|
|  └Bps|Float|16710625.733333332| Bandwidth data.

 Unit: bit/second

 |
|  └TimeStamp|String|2018-01-02T11: 04: 00Z| Time stamp.

 -   The date format follows the iso8601 representation and uses UTC time.
-   For example: 2016-10-20t04: 00: 00Z.

 |

Request Parameters return parameters

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeBpsData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Z&IspNameEn=telecom&LocationNameEn=beijingPublic request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Data":{
            "BpsModel":[
                
                    "Bps":16710625.733333332,
                    "TimeStamp":"2018-01-02T11:05:00Z"
                
                
                    "Bps":59392614.8,
                    "TimeStamp":"2018-01-02T11:04:00Z"
                
            
        
        "RequestId":"B49E6DDA-F413-422B-B58E-2FA23F286726"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


