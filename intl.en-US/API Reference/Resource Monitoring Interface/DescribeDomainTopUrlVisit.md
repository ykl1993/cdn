# DescribeDomainTopUrlVisit {#reference_ddf_g1n_vdb .reference}

Obtain the popular URL list for a CDN domain name on a specific day.

-   When StartTime is not specified, the interface reads data from the past day be default.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_hd5_t1n_vdb .section}

|Parameters|Type|Required| Example values|Description|
|Action|String|Yes|DescribeDomainTopUrlVisit|The name of this interface. Value: DescribeDomainTopUrlVisit|
|DomainName|String|No|test.test.com|Only one domain name is supported. If the parameter is left blank, the return results contain the combined data of all CDN domains by default.|
|SortBy|String|No|pv| Sorting manner.

 -   Supports traf and pv.
-   Default value: pv

 |
|StartTime|String|No|2015-12-03| Start time of data query, and adopts Beijing time.

 -   Format: YYYY-MM-DD.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_nqf_v1n_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|The ID of the request.|
|DomainName|String|test.com|CDN domain name.|
|StartTime|String|2015-12-03|Specified date of query.|
|AllUrlList| | |List of all popular URLs.|
|  └UrlDetail|String|[Http://test.com/nn\_live/nn\_x64/a0.m3u8](http://test.com/nn_live/nn_x64/a0.m3u8)|Complete URL.|
|  └VisitData|String|161673|Times of access.|
|  └VisitProportion|Float|0.35|Access proportion.|
|  └Flow|String|460486880| Traffic.

 Unit: byte

 |
|  └FlowProportion|Float|0.35|Traffic proportion.|
|Url200List| | |Returned URL list in 2xx format.|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8)|Complete URL.|
|  └VisitData|String|161673|Times of access.|
|  └VisitProportion|Float|0.35|Access proportion.|
|  └ Flow|String|460486880| Traffic.

 Unit: byte

 |
|  └FlowProportion|Float|0.35|Traffic proportion.|
|Url300List| | |Returned URL list in 3xx format.|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/a0.m3u8](http://test.com/nn_live/nn_x64/a0.m3u8)|Complete URL.|
|  └VisitData|String|161673|Times of access.|
|  └VisitProportion|Float|0.35|Access proportion.|
|  └Flow|String|460486880| Traffic.

 Unit: byte

 |
|  └FlowProportion|Float|0.35|Traffic proportion.|
|Url400List| | |Returned URL list in 4xx format.|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8)|Complete URL.|
|  └VisitData|String|1884|Times of access.|
|  └VisitProportion|Float|0.35|Access accounts.|
|  └Flow|String|460486880| Traffic. 

 Unit: byte

 |
|  └FlowProportion|Float|0.35|Traffic proportion.|
|Url500List| | |Returned URL list in 5xx format.|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8)|Complete URL.|
|  └VisitData|String|161673|Times of access.|
|  └VisitProportion|Float|0.35|Access proportion.|
|  └Flow|String|460486880| Traffic.

 Unit: byte

 |
|  └FlowProportion|Float|0.35|Traffic proportion.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit&DomainName=test.com
&StartTime=2015-12-03
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "AllUrlList":{
            "UrlList":[
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/a0.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"37",
                    "VisitProportion":0.35
                
            
        
        "DomainName":"test.com",
        "RequestId":"64D28B53-5902-409B-94F6-FD46680144FE",
        "StartTime":"2015-12-03",
        "Url200List":{
            "UrlList":[
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUDMlPTIwMTxMDk5ZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"3",
                    "VisitProportion":0.35
                
            
        
        "Url300List":{
            "TopUrlVisitModel":[]
        
        "Url400List":{
            "UrlList":[
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"1884",
                    "VisitProportion":0.35
                
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SEEwODgmpbmRleZPTE,/HNJSMPP360.ts",
                    "VisitData":"1",
                    "VisitProportion":0.35
                
            
        
        "Url500List":{
            "UrlList":[
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                
                
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"3",
                    "VisitProportion":0.35
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


