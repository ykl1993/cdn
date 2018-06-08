# DescribeDomainTopReferVisit {#reference_qls_jbn_vdb .reference}

Obtain the reference times ranking of popular pages for a CDN domain name on a specific day.

-   When StartTime is not specified, the interface reads data from the past day by default.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_nmz_kdn_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainTopReferVisit|The name of this interface.  Value: DescribeDomainTopReferVisit|
|DomainName|String|No|www.yourdomain.com|Only one domain name is supported. If the parameter is left blank, the return results contain the combined data of all CDN domains by default.|
|SortBy|String|No|pv| Sorting manner.

 -   Supports traf and pv.
-   Default value: pv

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| Start time of data query, and adopts Beijing time.

 -   Format: YYYY-MM-DD.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_lfx_qdn_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|95994621-8382-464B-8762-C708E73568D1|The ID of the request.|
|DomainName|String|test.com|CDN domain name.|
|StartTime|String|2015-11-28|Specified date of query.|
|TopReferList| | |List of all popular referer URLs.|
|  └ReferDetail|String|live-hunantv.cdnpe.com|Complete referer URL.|
|  └VisitData|String|3|Times of access.|
|  └VisitProportion|Float|0.5|Access proportion.|
|  └Flow|String|200| Traffic.

 Unit: byte

 |
|  └FlowProportion|Float|0.5|Traffic proportion.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainTopReferVisit&DomainName=test.com
&StartTime=2015-11-28
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DomainName":"test.com",
        "RequestId":"95994621-8382-464B-8762-C708E73568D1",
        "StartTime":"2015-11-28",
        "TopReferList":{
            "ReferList":[
                
                    "ReferDetail":"-",
                    "VisitData":"229567"
                
                
                    "ReferDetail":"123.57.158.8",
                    "VisitData":"2496"
                
                
                    "ReferDetail":"live-hunantv.cdnpe.com",
                    "VisitData":"448"
                
                
                    "ReferDetail":"video.ccdemo.ccgslb.net",
                    "VisitData":"3"
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


