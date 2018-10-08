# DeleteHttpHeaderConfig {#reference_sq1_fjl_vdb .reference}

Delete the Referer anti-leech configuration of a CDN domain.

## Request parameters {#section_eqx_gjl_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DeleteHttpHeaderConfig|The name of this interface. Value: DeleteHttpHeaderConfig|
|ConfigID|String|Yes|438205|ConfigID|
|DomainName|String|Yes|www.yourdomain.com|DomainName|

## Return parameters {#section_f11_jjl_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=DeleteHttpHeaderConfig
&DomainName=www.macaron.org.cn
&ConfigID=438205
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


