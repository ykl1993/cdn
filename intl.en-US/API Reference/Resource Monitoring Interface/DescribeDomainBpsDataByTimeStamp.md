# DescribeDomainBpsDataByTimeStamp {#reference_fzq_lfn_vdb .reference}

Obtain the bandwidth data of a CDN domain name on different locations and ISPs at specific time. The unit is bit/second.

-   Batch domain name query is not supported.
-   The time is precise to 5-minute granularity.

## Request parameters {#section_pzz_pfn_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainBpsDataByTimeStamp|The name of this interface. Value: DescribeDomainBpsDataByTimeStamp|
|DomainName|String|Yes.|www.yourdomain.com|Domain name to be queried. The value cannot be blank.|
|IspNames|String|Yes.|unicom,telecom| Target ISP lists to be queried, separated by commas \(,\). The value cannot be blank. 

 ISP names are obtained using the DescribeCdnRegionAndIsp interface.

 |
|LocationNames|String|Yes.|liaoning,guangxi| Target node lists to be queried, separated by commas \(,\). The value cannot be blank. 

 Location names are obtained using the DescribeCdnRegionAndIsp interface.

 |
|TimePoint|String|Yes.|2016-08-01T22:00Z| Target time point of query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.

 |

## Return parameters {#section_ffh_vfn_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|abc.cn|CDN domain name.|
|BpsDataList| | |The bps value corresponding to each Locate and ISP.|
|  └LocationName|String|Liaoning|Node name.|
|  └IspName|String|unicom|ISP name.|
|  └Bps|Long|52119553|Corresponding bandwidth value.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|
|TimeStamp|String|2017-12-22T08:00:00:00Z|Moment.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByTimeStamp&DomainName=abc.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&TimePoint=2016-08-01T22:00Z
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "BpsDataList":{
            "BpsDataModel":[
                
                    "Bps":880996111,
                    "IspName":"telecom",
                    "LocationName":"Liaoning"
                
                
                    "Bps":52119553,
                    "IspName":"unicom",
                    "LocationName":"Liaoning"
                
                
                    "Bps":51295137,
                    "IspName":"telecom",
                    "LocationName":"Guangxi"
                
                
                    "Bps":18673571,
                    "IspName":"unicom",
                    "LocationName":"Guangxi"
                
            
        
        "DomainName":"abc.cn",
        "RequestId":"7682DE14-3B4D-48D0-9B7C-DD3C8C3E1C78",
        "TimeStamp":"2016-08-01T22:00Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


