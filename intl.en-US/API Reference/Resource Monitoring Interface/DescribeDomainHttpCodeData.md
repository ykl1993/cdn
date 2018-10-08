# DescribeDomainHttpCodeData {#reference_pq4_h5m_vdb .reference}

Obtain the HTTP return code proportion of CDN domains. The minimum granularity is 5 minutes.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_gqh_n5m_vdb .section}

|Parameters|Type|Required |Example values|Description|
|Action|String|Yes|DescribeDomainHttpCodeData|The name of this interface. Value: DescribeDomainHttpCodeData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. Batch query is supported. Multiple domain names are separated by commas \(half width\).|
|EndTime|String|No|2015-11-30T05:40Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|Interval|String|No|300| Time granularity of data query.

 -   300s, 3600s, 14400s, 28800s and 86400s are supported.
-   When the parameter is left blank or when the value is not supported, the default value 300 seconds is used.

 |
|IspNameEn|String|No|unicom|Carrier name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all carriers are obtained.|
|LocationNameEn|String|No|beijing|Region name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all regions are obtained.|
|StartTime|String|No|2015-11-30T05:33Z| Start time of data query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.

 |
|TimeMerge|String|No|on| Value range:

 -   on: default value, indicating that the interval of each record can be merged based on the time span.
-   off: data of 5-min-granularity is returned, and the maximum time span is 31 days.

 |

## Return parameters {#section_et3_y5m_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|The ID of the request.|
|DomainName|String|test.test.com|Domain name.|
|DataInterval|String|300|Time interval.|
|StartTime|String|2015-11-30T05:33Z|Start time.|
|EndTime|String|2015-11-30T05:40Z|End time.|
|HttpCodeData| | |Data.|
|  └TimeStamp|String|2015-11-30T05:30:00Z|Timestamp.|
|  └Value| | |value.|
|   HTTP return code.|String|200|HTTP return code.|
|    └Proportion|String|66.046511627907|Proportion data.|
|    └Count|String|300|The total number.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainHttpCodeData&DomainName="test.com,abc.com"
&StartTime=2015-11-30T05:33Z
&EndTime=2015-11-30T05:40Z
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"300",
        "DomainName":"test.com,abc.com",
        "Endtime": "Maid: 40z ",
        "HttpCodeData":{
            "UsageData":[
                
                    "TimeStamp":"2015-11-30T05:40:00Z",
                    "Value":{
                        "CodeProportionData":[
                            
                                "Code":"200",
                                "Proportion":"66.046511627907"
                            
                            
                                "Code":"206",
                                "Proportion":"4.72868217054264"
                            
                            
                                "Code":"302",
                                "Proportion":"0.155038759689922"
                            
                            
                                "Code":"304",
                                "Proportion":"0.62015503875969"
                            
                            
                                "Code":"500",
                                "Proportion":"28.4496124031008"
                            
                        
                    
                
                
                    "TimeStamp":"2015-11-30T05:35:00Z",
                    "Value":{
                        "CodeProportionData":[
                            
                                "Code":"200",
                                "Proportion":"64.7822765469824"
                            
                            
                                "Code":"206",
                                "Proportion":"3.74331550802139"
                            
                            
                                "Code":"302",
                                "Proportion":"0.152788388082506"
                            
                            
                                "Code":"304",
                                "Proportion":"1.90985485103132"
                            
                            
                                "Code":"500",
                                "Proportion":"29.4117647058824"
                            
                        
                    
                
                
                    "TimeStamp":"2015-11-30T05:30:00Z",
                    "Value":{
                        "CodeProportionData":[
                            
                                "Code":"200",
                                "Proportion":"67.1458998935037"
                            
                            
                                "Code":"206",
                                "Proportion":"12.6730564430245"
                            
                            
                                "Code":"302",
                                "Proportion":"0.053248136315229"
                            
                            
                                "Code":"304",
                                "Proportion":"0.958466453674121"
                            
                            
                                "Code":"500",
                                "Proportion":"19.1693290734824"
                            
                        
                    
                
            
        
        "RequestId":"BC858082-736F-4A25-867B-E5B67C85ACF7",
        "StartTime":"2015-11-30T05:33Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


