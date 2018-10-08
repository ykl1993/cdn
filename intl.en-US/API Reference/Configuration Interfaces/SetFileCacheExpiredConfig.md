# SetFileCacheExpiredConfig {#reference_o3j_j2g_vdb .reference}

Set file expiration configuration.

## Request parameters {#section_bzz_bfg_vdb .section}

|Parameters|Type| Required|Example values|Description|
|Action|String|Yes|SetFileCacheExpiredConfig|The name of this interface. Value: SetFileCacheExpiredConfig|
|CacheContentCachecontent|String|Yes.|jpg, png|Filename suffixes, which are separated by commas \(,\).|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|
|TTL.|String|Yes.|600| Cache time configuation. 

 Unit: seconds

 |
|Weight|String|No|22| Weight of the configuration. 

 Value range: 1-99. A greater value indicates a higher priority. 

 Default value: 1

 |

## Return parameters {#section_jdc_3fg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetFileCacheExpiredConfig
&CacheContent=jpg%2Cpng
&DomainName=www.macaron.org.cn
&TTL=600
&Weight=50
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


