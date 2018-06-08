# DescribeDomainPathData {#reference_cqp_j3n_vdb .reference}

Obtain metric data of 5 minutes of CDN domain names path level, including traffic and times of accesses.

**Note:** The domain name with bandwidth of more than 10G, or GC6 and GC7 client can apply by submitting ticket or consult service manager.  

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is not supported.
-   Data from the past 30 days can be obtained at most.
-   Path information does not support fuzzy match.

## Request parameters {#section_ujn_t3n_vdb .section}

|Parameters|Type| Required| Example values|Description|
|Action|String|Yes|DescribeDomainPathData|The name of this interface.  Value: DescribeDomainPathData|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   Date is in ISO8601 format, and must use UTC time.
-   Start and end time, with an interval of less than 30 days.
-   Example: 2016-10-20T04:00:00Z.

 |
|PageNumber|Integer|No|1|Page number, starting from 1.|
|PageSize|Integer|No|20|Page size, not exceeding 1000.|
|Path|String|No|/path/| Path, beginning with virgule \(/\).

 -   If this parameter is left blank, all the paths are queried.
-   If the path is directory, it must end with virgule \(/\).

 |
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   Date is in ISO8601 format, and must use UTC time.
-   For example: 2016-10-20T04:00:00Z.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_gjg_z3n_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|test.test.com|CDN domain name.|
|StartTime|String|2017-09-30T17:00:00Z|Start time.|
|EndTime|String|2017-09-30T17:00:00Z|End time.|
|PageSize|Integer|20|Page size.|
|PageNumber|Integer|1.|The current page number, beginning with 1.|
|DataInterval|String|300| Time interval.

 Units: seconds

 |
|TotalCount|Integer|2|The total number of path bandwidth data.|
|PathDataPerInterval| | |The list of path bandwidth data.|
|  └Traffic|Integer|346|Traffic \(B\).|
|  └Acc|Integer|10|Times of accesses.|
|  └Path|String|/path/|Path.|
|  └Time|String|2017-09-30T16:00:00Z|Time.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

 https://cdn.aliyuncs.com?Action=DescribeDomainPathData&DomainName=<DomainName>&PageNumber=1&PageSize=20
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":300,
        "EndTime":"2017-09-30T17:00:00Z",
        "PageNumber":1,
        "PageSize":20,
        "PathDataPerInterval":{
            "UsageData":[
                
                    "Acc":10,
                    "Path":"/path/",
                    "Time":"2017-09-30T16:00:00Z",
                    "Traffic":346
                
                
                    "Acc":12,
                    "Path":"/path/",
                    "Time":"2017-09-30T16:05:00Z",
                    "Traffic":400
                
            
        
        "StartTime":"2017-09-30T16:00:00Z",
        "TotalCount":2
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


