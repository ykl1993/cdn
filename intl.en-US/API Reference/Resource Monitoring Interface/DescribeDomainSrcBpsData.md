# DescribeDomainSrcBpsData {#reference_ldq_2vl_vdb .reference}

Obtain the back-to-source bandwidth metric data of CDN domains. The unit is bit/second.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported \(at most 200 domain names one time\). Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_ijp_tnm_vdb .section}

|Name|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainSrcBpsData|The name of this interface. Value: DescribeDomainSrcBpsData|
|DomainName|String|No|www.yourdomain.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|EndTime|String|No|2017-12-12T20:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|FixTimeGap|String|No|false|Zero-padding is performed during download.|
|Interval|String|No|300|Time interval.|
|StartTime|String|No|2017-12-10T20:00Z| -   Start time of data query. 
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |
|TimeMerge|String|No|on| Value range:

 -   on: default value, indicating that the interval of each record can be merged based on the time span.
-   off: data of 5-min-granularity is returned, and the maximum time span is 31 days.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_dyz_24m_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|
|DomainName|String|yourdomain.com|Your CDN domain name information.|
|StartTime|String|2017-12-10T20:00Z|Start time.|
|EndTime|String|2017-12-12T20:00Z|End Time.|
|DataInterval|String|300|Interval of each record. The unit is seconds.|
|SrcBpsDataPerInterval| | |Back-to-source bandwidth data during each interval.|
|  └TimeStamp|String|2017-12-10T20:45:00Z|Start time of a time slice.|
|  └Value|String|500|Detailed usage data.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainSrcBpsData&DomainName=test.com
&StartTime=2017-12-10T20:00Z
&EndTime=2017-12-10T21:00Z
&public request parameters
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"300",
        "DomainName":"test.com",
        "EndTime":"2017-12-10T21:00Z",
        "RequestId":"7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
        "SrcBpsDataPerInterval":{
            "DataModule":[
                
                    "TimeStamp":"2015-12-10T21:00:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:35:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:50:00Z",
                    "Value": 821"
                
                
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:10:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:55:00Z",
                    "Value":"0"
                
                
                    "Timestamp": "Fig: 30: 00Z ",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:25:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:40:00Z",
                    "Value":"0"
                
                
                    "Timestamp": "Maid: 15: 00Z ",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:45:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:20:00Z",
                    "Value":"0"
                
            
        
        "StartTime":"2017-12-10T20:00Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message:" The request processing has failed due to some unknown error .",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


