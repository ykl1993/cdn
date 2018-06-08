# DescribeDomainFileSizeProportionData {#reference_mxw_wdn_vdb .reference}

Obtain the file size shares of a CDN domain name. The minimum granularity is 1 hour.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_nnl_b2n_vdb .section}

|Parameters|Type| Required| Example values|Description|
|Action|String|Yes|Describedomainfilesizeproportiondata|The name of this interface.  Value: DescribeDomainFileSizeProportionData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, all domain names belonging to the current user are queried.|
|EndTime|String|No|2015-11-30T05:40Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|StartTime|String|No|2015-11-30T01:33Z| Start time of data query.

 -   The date format adopts ISO8601 notation and adopts the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   The minimum data granularity is 1 hour.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_s1w_g2n_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|23ACE7E2-2302-42E3-98F8-E5E697FD86C3|The ID of the request.|
|DomainName|String|test.test.com|CDN domain name.|
|DataInterval|String|3600|Interval of each record. The value is invariably set to 1 hour or 1 day.|
|StartTime|String|2015-11-30T01:33Z|Start time of data query.|
|EndTime|String|2015-11-30T05:40Z|End time of data query.|
|FileSizeProportionDataInterval| | |Data accessed per second during each interval.|
|  └ Timestamp|String|2015-11-30T03:00:00Z|Start time of a time slice.|
|  └Value| | |Data list of file size proportion.|
|    └FileSize|String|<50K|File size.|
|    └Proportion|String|0.01|Proportion.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainFileSizeProportionData&DomainName=test.com
&StartTime=2015-11-30T01:33Z
&EndTime=2015-11-30T05:40Z
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"3600",
        "DomainName":"test.com",
        "EndTime":"2015-11-30T05:40Z",
        "FileSizeProportionDataInterval":{
            "UsageData":[
                
                    "TimeStamp":"2015-11-30T03:00:00Z",
                    "Value":{
                        "FileSizeProportionData":[
                            
                                "FileSize":"<1M",
                                "Proportion":"7.91"
                            
                            
                                "FileSize":"<20K",
                                "Proportion":"0.137"
                            
                            
                                "FileSize":"<5K",
                                "Proportion":"64.544"
                            
                            
                                "FileSize":">1M",
                                "Proportion":"21.334"
                            
                            
                                "FileSize":"<10K",
                                "Proportion":"0.01"
                            
                            
                                "FileSize":"<50K",
                                "Proportion":"0.02"
                            
                            
                                "FileSize":"<100K",
                                "Proportion":"6.046"
                            
                        
                    
                
                
                    "TimeStamp":"2015-11-30T04:00:00Z",
                    "Value":{
                        "FileSizeProportionData":[
                            
                                "FileSize":"<1M",
                                "Proportion":"4.564"
                            
                            
                                "FileSize":"<20K",
                                "Proportion":"0.645"
                            
                            
                                "FileSize":"<5K",
                                "Proportion":"69.746"
                            
                            
                                "FileSize":">1M",
                                "Proportion":"18.534"
                            
                            
                                "FileSize":"<10K",
                                "Proportion":"0.01"
                            
                            
                                "FileSize":"<50K",
                                "Proportion":"0.068"
                            
                            
                                "FileSize":"<100K",
                                "Proportion":"6.432"
                            
                        
                    
                
                
                    "TimeStamp":"2015-11-30T02:00:00Z",
                    "Value":{
                        "FileSizeProportionData":[
                            
                                "FileSize":"<1M",
                                "Proportion":"16.066"
                            
                            
                                "FileSize":"<20K",
                                "Proportion":"0.07"
                            
                            
                                "FileSize":"<5K",
                                "Proportion":"52.842"
                            
                            
                                "FileSize":">1M",
                                "Proportion":"26.43"
                            
                            
                                "FileSize":"<10K",
                                "Proportion":"0.018"
                            
                            
                                "FileSize":"<50K",
                                "Proportion":"0.026"
                            
                            
                                "FileSize":"<100K",
                                "Proportion":"4.547"
                            
                        
                    
                
                
                    "TimeStamp":"2015-11-30T05:00:00Z",
                    "Value":{
                        "FileSizeProportionData":[
                            
                                "FileSize":"<1M",
                                "Proportion":"4.521"
                            
                            
                                "FileSize":"<20K",
                                "Proportion":"1.551"
                            
                            
                                "FileSize":"<5K",
                                "Proportion":"68.254"
                            
                            
                                "FileSize":">1M",
                                "Proportion":"18.625"
                            
                            
                                "FileSize":"<10K",
                                "Proportion":"0.631"
                            
                            
                                "FileSize":"<50K",
                                "Proportion":"0.026"
                            
                            
                                "FileSize":"<100K",
                                "Proportion":"6.392"
                            
                        
                    
                
            
        
        "RequestId":"23ACE7E2-2302-42E3-98F8-E5E697FD86C3",
        "StartTime":"2015-11-30T01:33Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


