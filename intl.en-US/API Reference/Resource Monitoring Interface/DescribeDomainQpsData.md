# DescribeDomainQpsData {#reference_an5_gtm_vdb .reference}

Obtain the times of access to a CDN domain per second. The value is expressed in QPS.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_b34_ptm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainQpsData|The name of this interface. Value: DescribeDomainQpsData|
|DomainName|String|No|test.test.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|DomainType|String|No|dynamic| Query type.

 -   If the parameter is set to "dynamic", the system queries the QPS of dynamic resources during full-site acceleration.
-   If the parameter is left blank, the system queries the QPS of static resources.

 |
|EndTime|String|No|2015-12-10T21:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|FixTimeGap|String|No|false|Zero-padding.|
|Interval|String|No|300| Time granularity of data query.

 -   300s, 3600s, 14400s, 28800s and 86400s are supported.
-   When the parameter is left blank or when the value is not supported, the default value 300 seconds is used.

 |
|IspNameEn|String|No|unicom|Carrier name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all carriers are obtained.|
|LocationNameEn|String|No|beijing|Region name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all regions are obtained.|
|StartTime|String|No|2015-12-10T20:00Z| Start time of data query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.

 |
|TimeMerge|String|No|on| Time range:

 -   on: default value, indicating that the interval of each record can be merged based on the time span.
-   off: data of 5-min-granularity is returned, and the maximum time span is 31 days.

 |

## Return parameters {#section_xzj_b5m_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|B8333EDB-4595-46E0-AFE9-29BAA290D0E0|The ID of the request.|
|DomainName|String|test.test.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|DataInterval|String|300|Interval of each record. The unit is seconds.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|EndTime|String|2015-12-10T21:00Z|End time.|
|QpsDataInterval| | |Times of access \(expressed in QPS\) to a CDN domain per second during each interval.|
|  └TimeStamp|String|2015-12-10T21:00:00Z|Start time of a time slice.|
|  └Value|String|0|Total QPS.|
|  └DomesticValue|String|0|QPS in China.|
|  └OverseasValue|String|0|QPS outside China.|
|  └AccValue|String|0|Total times of access.|
|  └AccDomesticValue|String|0|Times of access in China.|
|  └AccOverseasValue|String|0|Times of access outside China.|
|  └DynamicValue|String|0|Dynamic QPS data value during full-site acceleration.|
|  └DynamicDomesticValue|String|0|Bandwidth dynamic QPS in China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └DynamicOverseasValue|String|0|Bandwidth dynamic QPS during full-site acceleration outside China. The value is blank when it is queried by regional carrier.|
|  └StaticValue|String|0|Static QPS data value during full-site acceleration. Unit: bit/second.|
|  └StaticDomesticValue|String|0|Bandwidth static QPS in China during full-site acceleration. The value is blank when it is queried by regional carrier.|
|  └StaticOverseasValue|String|0|Bandwidth static QPS during full-site acceleration outside China. The value is blank when it is queried by regional carrier.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainQpsData&DomainName=test.com
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
        "QpsDataInterval":{
            "DataModule":[
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T21:00:00Z",
                    "Value":"0.56"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:35:00Z",
                    "Value":"0.64"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:50:00Z",
                    "Value":"0.4"
                
                
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"1.0033333333333334"
                
            
        
        "RequestId":"BEA5625F-8FCF-48F4-851B-CA63946DA664",
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


