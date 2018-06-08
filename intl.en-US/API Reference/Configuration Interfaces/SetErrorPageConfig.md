# SetErrorPageConfig {#reference_erv_kbg_vdb .reference}

Set custom 404 page redirect for a CDN domain.

## Request parameters {#section_myj_mbg_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetErrorPageConfig|The name of this interface.  Value: SetErrorPageConfig|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|
|Pagetype|String|Yes.|default| Error page type.  Value:

 -   default: default page
-   charity: public welfare page
-   other: custom page

 |
|CustomPageUrl|String|No|[http://www.macaron.org.cn/notfound.html](http://www.macaron.org.cn/notfound.html)|URL of the custom page for redirect after an error occurs \(complete path under the CDN domain name\).|

## Return parameters {#section_mns_ccg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetErrorPageConfig
&DomainName=www.macaron.org.cn
&CustomPageUrl=http://www.macaron.org.cn/notfound.html
&PageType=other
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


