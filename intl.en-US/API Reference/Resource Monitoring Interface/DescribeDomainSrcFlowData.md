# DescribeDomainSrcFlowData {#reference_ihj_44m_vdb .reference}

Obtain the back-to-source traffic metric data on a CDN domain in bits.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_w3t_tqm_vdb .section}

|Name|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainSrcFlowData|The name of this interface.  Value: DescribeDomainSrcFlowData|
|DomainName|String|No|www.yourdomain.com| -   If the parameter is left blank, the system returns the combined data of all CDN domains by default.
-   You can enter CDN domains to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|FixTimeGap|String|No|false|Whether zero-padding is performed.|
|Interval|String|No|300|The time interval.|
|StartTime|String|No|2017-12-21T08:00:00:00Z| -   Start time of data query.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |
|TimeMerge|String|No|true|Whether the time is merged.|
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_wgn_2rm_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|test.com|CDN domain name information.|
|DataInterval|String|300|Interval of each record. The unit is seconds.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|EndTime|String|2015-12-10T21:00Z|End time.|
|SrcFlowDataPerInterval| | |Back-to-source traffic data during each interval.|
|  └TimeStamp|String|2017-12-22T08:00:00:00Z|Start time of a time slice.|
|  └Value|String|0|Detailed usage data.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainSrcFlowData&DomainName=test.com
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
        "RequestId":"A666D44F-19D6-490E-97CF-1A64AB962C57",
        "SrcFlowDataPerInterval":{
            "DataModule":[
                
                    "TimeStamp":"2015-12-10T21:00:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:35:00Z",
                    "Value": "0"
                
                
                    "TimeStamp":"2015-12-10T20:50:00Z",
                    "Value":"33886"
                
                
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:10:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:55:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:30:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:25:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:40:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:15:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:45:00Z",
                    "Value":"0"
                
                
                    "TimeStamp":"2015-12-10T20:20:00Z",
                    "Value":"0"
                
            
        
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


