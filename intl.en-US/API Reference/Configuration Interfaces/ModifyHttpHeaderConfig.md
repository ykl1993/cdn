# ModifyHttpHeaderConfig {#reference_tbh_p3l_vdb .reference}

Modify custom HTTP headers.

## Request parameters {#section_bxg_r3l_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|ModifyHttpHeaderConfig|The name of this interface. Value: ModifyHttpHeaderConfig|
|ConfigID|String|Yes.|892783|Configuration ID to be modified.|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|
|HeaderKey|String|Yes.|content-type| HTTP header parameter. Value:

 -   content-type
-   cache-control
-   content-disposition
-   content-language
-   expires
-   access-control-allow-origin
-   access-control-allow-methods
-   access-control-max-age

 |
|HeaderValue|String|Yes.|application|HTTP header parameter value.|

## Return parameters {#section_ih1_z3l_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=ModifyHttpHeaderConfig
&DomainName=www.macaron.org.cn
&HeaderKey=content-type
&headerValue=application
&ConfigID=892783
&public request parameters
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


