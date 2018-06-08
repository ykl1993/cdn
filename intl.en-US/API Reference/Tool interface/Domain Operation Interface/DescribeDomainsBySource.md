# DescribeDomainsBySource {#reference_hpj_gty_5db .reference}

Query the list of all domain names corresponding to the source sites under a user account name. Fuzzy match is not supported.  The API allows you to query multiple source sites, which are separated by commas \(,\).

## Request parameters {#section_aqw_lty_5db .section}

|Parameters|Type|Required|**Example values**|**Description**|
|:---------|:---|:-------|:-----------------|:--------------|
|Action|String|Yes|DescribeDomainsBySource| The name of this interface.  Value: 

 DescribeDomainsBySource

 |
|Sources|String|Yes|aaa.source.com| Source site. Multiple source sites are separated by comma.

 |

## Return Parameters {#section_gp2_vty_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|B0F074E5-A1AC-4B32-8EA2-6F450410D1E0| The ID of the request.

 |
|Sources|String|aaa.source.com,b.source.com| A source site, which is requested.

 |
|DomainsList| | | Returns the list of domain names corresponding to source sites, in the format of an array consisting of DomainsData.

 |
|└Source|String|b.source.com| A source site, which is requested.

 |
|└Domains|String|b1.com| Returns the list of domain name corresponding to a domain name, in the ormat of a list consisting of domainNames.

 |
|└DomainInfos| | | Returns the domain detailed information, in th format of a list consisting of domainInfo.

 |
|  └DomainName|String|Returns the domain detailed information, in the format of a list consisting of domainInfo.| Domain name.

 |
|└Status|String|online| The status of the domain name.

 |
|└CreateTime|String|2016-07-12T11:53:19+08:00| Creation time

 |
|└UpdateTime|String|2017-03-31T04:49:00+08:00| The update time.

 |
|└DomainCname|String|b1.com.w.alikunlun.com| CNAME.

 |

## Examples {#section_zvg_45y_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=DescribeDomainsBySource&Sources=aaa.source.com,b.source.com&Public request example
```

**Normal return example**

-   JSON format

    ```
    
        "Domainslist ":{
            "DomainsData":[
                
                    "Domaininfos ":{
                        "domainInfo":[{
                            "CreateTime":"2016-07-12T11:53:19+08:00",
                            "DomainCname":"a1.w.kunlunar.com",
                            "DomainName":"a1.com",
                            "Status": "Pending",
                            "UpdateTime":"2017-03-31T04:49:00+08:00"
                        
                    
                    "Domains":{
                        "domainNames":["a1.com"]
                    
                    "Source":"aaa.source.com"
                
                
                    "DomainInfos":{
                        "domainInfo":[{
                            "CreateTime":"2017-01-13T18:01:00+08:00",
                            "DomainCname":"b1.com.w.alikunlun.com",
                            "DomainName":"b1.com",
                            "Status":"online",
                            "UpdateTime":"2017-01-17T21:16:16+08:00"
                        
                    
                    "Domains":{
                        "domainNames":["b1.com"]
                    
                    "Source":"b.source.com"
                
            
        
        "RequestId":"B0F074E5-A1AC-4B32-8EA2-6F450410D1E0",
        "Sources":"aaa.source.com,b.source.com"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


