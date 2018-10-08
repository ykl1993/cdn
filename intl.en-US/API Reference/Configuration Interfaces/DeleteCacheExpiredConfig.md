# DeleteCacheExpiredConfig {#reference_dvq_53g_vdb .reference}

Delete a custom cache policy.

## Request parameters {#section_xjc_mjg_vdb .section}

|Parameters|Type| Required|Example values|Description|
|Action|String|Yes|DeleteCacheExpiredConfig|The name of this interface. Value: DeleteCacheExpiredConfig|
|CacheType|String|Yes.|suffix| Cached content type.  Value:

 -   suffix: filename suffix.
-   path: path. Directory and complete path are supported.

 |
|ConfigID|String|Yes.|903423|Configuration ID. This parameter need not be specified for the Add operation, but must be specified for the Modify operation.|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|

## Return parameters {#section_ntd_gxg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=DeleteCacheExpiredConfig
&CacheType=path
&ConfigID=903423
&DomainName=www.macaron.org.cn
&public request parameter
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


