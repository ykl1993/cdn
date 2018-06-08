# DescribeDomainBpsData {#reference_ugf_f4l_vdb .reference}

Obtain the network bandwidth metric data of a CDN domain. The unit is bit/second.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_cd5_1tl_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainBpsData|The name of this interface.  Value: DescribeDomainBpsData|
|DomainName|String|No|test.test.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|DomainType|String|No|dynamic| Query type.

 -   If the parameter is set to “dynamic”, the system queries the real-time bandwidth of dynamic and static resources during full-site acceleration.
-   If the parameter is left blank, the system queries the real-time bandwidth of static resources.

 |
|EndTime|String|No|2015-12-10T20:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|FixTimeGap|String|No|false|Whether zero-padding is performed.|
|Interval|String|No|300| Time granularity of data query.

 -   300s, 3600s, 14400s, 28800s and 86400s are supported.
-   When the parameter is left blank or when the value is not supported, the default value 300 seconds is used.

 |
|IspNameEn|String|No|telecom|Carrier name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all carriers are obtained.|
|LocationNameEn|String|No|beijing|Region name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all regions are obtained.|
|StartTime|String|No|2015-12-10T20:00Z| Start time of data query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |
|TimeMerge|String|No|on| Value range:

 -   on: default value, indicating that the interval of each record can be merged based on the time span.
-   off: data of 5-min-granularity is returned, and the maximum time span is 31 days.

 |

## Return parameters {#section_k4x_2tl_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|Request ID|
|Domainname|String|test.test.com|Your CDN domain name.|
|DataInterval|String|300|The interval rule needs to be supplemented. Interval of each record. The unit is seconds.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|End time.|String|2015-12-10T20:00Z|End time.|
|LocationNameEn|String|beijing|Region name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all regions are obtained.|
|IspNameEn|String|unicom|Carrier name in English, which is obtained using the DescribeCdnRegionAndIsp interface. If the parameter is left blank, the English names of all carriers are obtained.|
|LocationName|String|The city of Beijing.|Region name.|
|IspName|String|unicom|Carrier name.|
|BpsDataPerInterval| | |Network bandwidth data of each interval.|
|  └TimeStamp|String|2015-12-10T20:00:00Z|Start time of a time slice.|
|└Value|String|11288111| bps data value.

 Unit: bit/second

 |
|└DomesticValue|String|11286111|Bandwidth bps in China. This value is blank when it is queried by regional carrier.|
|  └OverseasValue|String|2000|Bandwidth bps outside China. This value is blank when it is queried by regional carrier.|
|  └DynamicValue|String|0| Dynamic bps data value during full-site acceleration. 

 Unit: bit/second

 |
|└DynamicDomesticValue|String|0|Station-wide acceleration, domestic Bandwidth Dynamic BPS, this value is empty when querying by regional operator.|
|└DynamicOverseasValue|String|0|Bandwidth dynamic bps outside China during full-site acceleration. This value is blank when it is queried by regional carrier.|
|  └StaticValue|String|0| Static bps data value during full-site acceleration.

 Unit: bit/second

 |
| └StaticDomesticValue|String|0|Bandwidth static bps in China during full-site acceleration. This value is blank when it is queried by regional carrier.|
|└StaticOverseasValue|String|0|Bandwidth static bps outside China during full-site acceleration. This value is blank when it is queried by regional carrier.|
|└L2Value|String|0| L2 bps data value. 

 Unit: bit/second

 |
|  └DomesticL2Value|String|0|L2 bandwidth bps in China. This value is blank when it is queried by regional carrier.|
|  └OverseasL2Value|String|0|L2 bandwidth bps outside China. This value is blank when it is queried by regional carrier.|
|SupplyBpsDatas| | |Supplement the reference data of real-time bandwidth from the past 30 minutes, which may not exist.|
|  └TimeStamp|String|2015-12-10T20:00:00Z|Start time of a time slice|
|  └Value|String|11288111| bps data value. 

 Unit: bit/second

 |

## Examples {#section_qrj_jtl_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainBpsData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "BpsDataPerInterval":{
            "DataModule":[
                
                    "DomesticL2Value":"0",
                    "DomesticValue":"11286111",
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "L2Value":"0",
                    "OverseasL2Value":"0",
                    "OverseasValue":"2000",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"11288111"
                
                
                    "DomesticL2Value":"0",
                    "DomesticValue":"12112821",
                    "DynamicDomesticValue":"0",
                    "DynamicOverseasValue":"0",
                    "DynamicValue":"0",
                    "L2Value":"0",
                    "OverseasL2Value":"0",
                    "OverseasValue":"12000",
                    "StaticDomesticValue":"0",
                    "StaticOverseasValue":"0",
                    "StaticValue":"0",
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"12124821"
                
            
        
        "DataInterval":"300",
        "DomainName":"test.com",
        "EndTime":"2015-12-10T21:00Z",
        "RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
        "StartTime":"2015-12-10T20:00Z",
        "SupplyBpsDatas":{
            "DataModule":[
                
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"12124821"
                
                
                    "TimeStamp":"2015-12-10T20:06:00Z",
                    "Value":"12144838"
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


