# SetPathCacheExpiredConfig {#reference_cjz_pfg_vdb .reference}

Modify directory expiration configuration.

## Request parameters {#section_osy_tfg_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|Setpathcacheexpiredconfig|The name of this interface. Value: SetPathCacheExpiredConfig|
|CacheContent|String|Yes.|/static/html/|Enter the path.|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|
|TTL.|String|Yes.|600| Cache time configuration. 

 Unit: seconds

 |
|Weight|String|No|22| Weight of the configuration. 

 Value range: 1-99. A greater value indicates a higher priority. 

 Default value: 1

 |

## Return parameters {#section_kxv_xfg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetPathCacheExpiredConfig
&CacheContent=%2Fstatic%2Fhtml%2F
&DomainName=www.macaron.org.cn
&TTL=600
&Weight=50
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


