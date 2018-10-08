# SetHttpHeaderConfig {#reference_ery_zgl_vdb .reference}

Set custom HTTP headers.

## Request parameters {#section_u4z_2hl_vdb .section}

|Parameters|Type|Required|Example value|Description|
|Action|String|Yes|SetHttpHeaderConfig|The name of this interface. Value: SetHttpHeaderConfig|
|Domainname|String|Yes|www.yourdomain.com|Your CDN domain name.|
|Headerkey|String|Yes|Content-Type| HTTP header parameter. Value:

 -   Content-Type
-   Cache-control
-   Content-Disposition
-   Content-language
-   Expires
-   Access-control-allow-Origin
-   Step 4: Parameters configuration Access-Control-Allow-Methods:
-   Access-control-allow-headers
-   Access-control-max-age
-   Access-control-expose-headers
-   Access-control-allow-Credentials

 |
|Headervalue|String|Yes|application|HTTP header parameter value.|

## Return parameters {#section_cgc_33l_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Example {#section_g1p_gcg_vdb .section}

**Request example**

```

Http://cdn.aliyuncs.com /? Action = fig
& Domainname = maid
& Headerkey = Content-Type
& Headervalue = Application
&CommonParameters
```

**Normal return sample**

-   JSON format

    ```
    
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
    
    ```


**Exception return sample**

-   JSON format

    ```
    
        "Code": "internalerror ",
        "Hostid": "maid ",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


