# Querying traffic monitoring data {#reference_fqg_5tl_vdb .reference}

Obtain the network traffic metric data of a CDN domain. The unit is bytes.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_ukl_d5l_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainFlowData|The name of this interface. Value: DescribeDomainFlowData|
|DomainName|String|No|www.yourdomain.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|DomainType|String|No|dynamic| Query type.

 -   If the parameter is set to “dynamic”, the system queries the real-time traffic of dynamic and static resources during full-site acceleration.
-   If the parameter is left blank, the system queries the real-time traffic of static resources.

 |
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|FixTimeGap|String|No|false|Whether zero-padding is performed.|
|Interval|String|No|300| -   Time granularity of data query.
-   300s, 3600s, 14400s, 28800s and 86400s are supported.
-   When the parameter is left blank or when the value is not supported, the default value 300 seconds is used.

 |
|IspNameEn|String|No|unicom|Carrier name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all carriers are obtained.|
|LocationNameEn|String|No|beijing|Region name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all regions are obtained.|
|StartTime|String|No|2017-12-21T08:00:00:00Z| Start time of data query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |
|TimeMerge|String|No|on| Value range:

 -   on: default value, indicating that the interval of each record can be merged based on the time span.
-   off: data of 5-min-granularity is returned, and the maximum time span is 31 days.

 |

## Return parameters {#section_h5x_g5l_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|test.com|Your CDN domain name information.|
|DataInterval|String|300|Interval of each record. The unit is seconds.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|EndTime|String|2015-12-10T21:00Z|End time.|
|FlowDataPerInterval| | |Traffic data during each time interval.|
|  └TimeStamp|String|2017-12-22T08:00:00:00Z|Start time of a time slice.|
|  └Value|String|423304182|Total traffic.|
|  └DomesticValue|String|0|Traffic in China.|
|  └OverseasValue|String|0|Traffic outside China.|
|  └DynamicValue|String|0|Dynamic traffic during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └DynamicDomesticValue|String|0|Dynamic traffic in China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └DynamicOverseasValue|String|0|Dynamic traffic outside China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └StaticValue|String|0|Static traffic during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └StaticDomesticValue|String|0|Static traffic in China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └StaticOverseasValue|String|0|Static traffic outside China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainFlowData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"300",
        "DomainName":"test.com",
        "EndTime":"2015-12-10T21:00Z",
        "FlowDataPerInterval":{
            "DataModule":[
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"423304182"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"454680793"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:10:00Z",
                    "Value":"501718342"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:15:00Z",
                    "Value":"434816025"
                
            
        
        "RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E",
        "StartTime":"2015-12-10T20:00Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


