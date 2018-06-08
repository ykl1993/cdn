# DescribeDomainSlowRatio {#reference_qg3_kzs_vdb .reference}

Obtain slow ration of video CDN domain names with 5-minute granularity.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is not supported.
-   Data from the past 30 days can be obtained at most.

## Request parameters {#section_mdq_qzs_vdb .section}

|Parameters|Type|Required| Example values|Description|
|Action|String|Yes|DescribeDomainSlowRatio|The name of this interface. Value: DescribeDomainSlowRatio|
|DomainName|String|Yes.|test.test.com|CDN domain name.|
|EndTime|String|No|2016-10-20T04:00:00Z| End time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   The time interval between the start time and end time is less than 30 days.
-   Example: 2016-10-20T04:00:00Z.

 |
|PageNumber|Integer|No|1|Page number, starting from 1.|
|PageSize|Integer|No|20|Page size.|
|StartTime|String|No|2016-10-20T04:00:00Z| Start time.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_cvq_vzs_vdb .section}

|Parameters|Type|Example values|Description|
|EndTime|String|017-09-30T16:00:00Z|End time.|
|DataInterval|Integer|300| Time interval. 

 Units: seconds

 |
|PageNumber|Integer|1.|The current page number, beginning with 1.|
|PageSize|Integer|20.|Page size.|
|TotalCount|Integer|2|The total number of slow ratio data.|
|StartTime|String|017-09-30T16:00:00Z|Start time.|
|SlowRatioDataPerInterval| | |List of slow ratio data.|
|  └TotalUsers|Integer|15|The total number of users.|
|  └SlowUsers|Integer|3|Number of slow users.|
|  └SlowRatio|Float|0.2|Slow ratio.|
|  └RegionNameZh|String|The city of Beijing|Region information in Chinese.|
|  └RegionNameEn|String|beijing|Region information in English.|
|  └IspNameZh|String| Unicom|ISP information in Chinese.|
|  └IspNameEn|String|unicom|ISP information in English.|
|  └Time|String|2017-09-30T16:00:00Z|Time.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=DescribeDomainSlowRatio&DomainName=&PageNumber=1&PageSize=20
```

**Normal request example**

-   JSON format

    ```
    
        "DataInterval":300,
        "EndTime":"2017-09-30T17:00:00Z",
        "PageNumber":1,
        "PageSize":20,
        "SlowRatioDataPerInterval":{
            "SlowRatioData":[
                
                    "IspNameEn":"telecom",
                    "IspNameZh":"Telecom",
                    "RegionNameEn":"guangdong",
                    "RegionNameZh":"Guangdong province",
                    "SlowRatio":0.1,
                    "SlowUsers":2,
                    "Time":"2017-09-30T16:00:00Z",
                    "TotalUsers":20
                
                
                    "IspNameEn":"unicom",
                    "IspNameZh":"Unicom",
                    "RegionNameEn":"beijing",
                    "RegionNameZh":"The city of Beijing",
                    "SlowRatio":0.2,
                    "SlowUsers":3,
                    "Time":"2017-09-30T16:00:00Z",
                    "TotalUsers":15
                
            
        
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


