# DescribeUserDomains {#reference_vys_stw_5db .reference}

Query all the domain names and statuses under a user name.  Support domain name fuzzy match filtering and domain name status filtering.  The domain name status includes:

-   running \(indicates the domain name service is normal and can be used\)
-   stopped
-   configuring
-   configure\_failed
-   Checking
-   Checking\_failedVerifying

## Request parameters {#section_prx_dxw_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|DescribeUserDomains| The name of this interface.  Value: 

 DescribeUserDomains

 |
|CdnType|String|No|web| CDN business type, separated by comma.

 |
|CheckDomainShow|Boolean|No|true| Whether the domain name at the checking status is shown.

 |
|DomainName|String|No|www.yourdomain.com| Domain name fuzzy match filtering.

 |
|Domainsearchtype|String|No|fuzzy\_match| Domain name search type:

-   fuzzy\_match: fuzzy match
-   pre\_match: pre-match
-   suf\_match: suf-match
-   full\_match: fully match

Default: puzzling y\_match

 |
|DomainStatus|String|No|online| The domain name status filtering.

 |
|FuncFilter|String|No|config| Filtering, supports config and unconfig.

-   config indicates funcid is activated, 
-   and unconfig indicates the funcid is not activated.

 |
|Funcid|String|No|98| funcid, such as the picture porn-detection function 98.

 |
|PageNumber|Integer|No|1| The page number.  

 Range value: 1~100000

 |
|PageSize|Integer|No|20| The page size.

 Range value: random integer between 1 and 50. 

 Maximum: 50

 Default value: 20Default: 20

 |
|ResourceGroupId|String|No|Your maid| Resource group ID.

 |
|Sources|String|No|a.b.com| Query according to the return source address.

 |

## Search according to the source address. {#section_jtq_2xw_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|AA75AADB-5E25-4970-B480-EAA1F5658483| The ID of the request.

 |
|PageNumber|Long|1| The page number of the return data.

 |
|PageSize|Long|5| The size of the whole page.

 |
|TotalCount|Long|16| The total number.

 |
|Domains| | | The total number.

 |
| └DomainName|String|onlytest.cdnpe.com| The CDN domain name.

 |
|└Cname|String|onlytest.cdnpe.com.w.alikunlun.net| The CNAME corresponding to the CDN domain name.

 |
|└CdnType|String|video| Acceleration business type.  Value range:

-   web: acceleration of images and small files
-   download: acceleration of large file downloads
-   video: acceleration of audio and video on demand
-   livestream: acceleration of live streaming media
-   httpsdelivery: HTTPS security acceleration

 |
|└DomainStatus|String|online| CDN domain name status.  Value:

-   online: activating
-   offline: deactivating
-   configuring: configuring
-   configure\_failed: configuration failed
-   checking: checking
-   check\_failed: checking failed

 |
|└GmtCreated|String|2015-10-28T09:31:59Z| The creation time of CDN domain name.

 |
|└GmtModified|String|2015-10-28T11:05:50Z| The modification time of CDN domain name.

 |
|└Description|String|Audit Failed| The reason of checking failure.

 |
| └ResourceGroupId|String|abcd1234abcd1234| The resource group ID.

 |
|└SourceType|String|oss| The source site type.

 |
|└SslProtocol|String|on| Switch.

 |
|└Sandbox|String|N/A| Sandbox.

 |
|└Sources|String|\{ “Source”: \[ “a.b.com” \] \}| Source site information.

 |

## Examples {#section_mwd_pcx_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=DescribeUserDomains&PageNumber=1&PageSize=5&DomainSearchType=fuzzy_match&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Domains":{
            "PageData":[
                
                    "CdnType":"download",
                    "Description":"audit failed",
                    "DomainName":"image.ddd.cdnpe.com",
                    "DomainStatus":"configure_failed",
                    "GmtCreated":"2015-10-28T09:32:51Z",
                    "GmtModified":"2015-10-28T11:05:52Z",
                    "ResourceGroupId":"abcd1234abcd1234"
                
                
                    "CdnType":"web",
                    "DomainName":"aadda.cdnpe.com",
                    "DomainStatus":"configure_failed",
                    "GmtCreated":"2015-10-28T09:31:59Z",
                    "GmtModified":"2015-10-28T11:05:50Z",
                    "ResourceGroupId":"abcd1234abcd1234"
                
                
                    "CdnType":"video",
                    "Cname":"onlytest.cdnpe.com.w.alikunlun.net",
                    "DomainName":"onlytest.cdnpe.com",
                    "DomainStatus":"online",
                    "GmtCreated":"2015-10-23T09:30:00Z",
                    "Gmtmodified": "2015-10-27t06: 34z ",
                    "ResourceGroupId":"abcd1234abcd1234"
                
                
                    "CdnType":"video",
                    "Cname":"test11.cdnpe.com.w.kunlunAr.com",
                    "DomainName":"test11.cdnpe.com",
                    "DomainStatus":"online",
                    "GmtCreated":"2015-10-23T09:23:20Z",
                    "Gmtmodified": "2015-10-23t09: 29z ",
                    "ResourceGroupId":"abcd1234abcd1234"
                
                
                    "CdnType":"video",
                    "Cname":"test.aliyun.com.w.alikunlun.com",
                    "DomainName":"test.aliyun.com",
                    "DomainStatus":"online",
                    "GmtCreated":"2015-10-23T09:01:57Z",
                    "GmtModified":"2015-10-23T09:02:11Z",
                    "ResourceGroupId":"abcd1234abcd1234"
                
            
        
        "PageNumber":1,
        "PageSize":5,
        "RequestId":"AA75AADB-5E25-4970-B480-EAA1F5658483",
        "TotalCount":16
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "Requestid": "maid"
    
    ```


