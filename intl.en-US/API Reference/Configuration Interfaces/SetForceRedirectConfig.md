# SetForceRedirectConfig {#reference_qvw_ncg_vdb .reference}

Set the force redirect method, and currently support HTTP and HTTPS force redirects.

**Note:** Force redirect can be enabled only after the user has uploaded a certificate and the certificate is enabled.

## Request parameters {#section_b1s_vcg_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetForceRedirectConfig|The name of this interface.  Value: SetForceRedirectConfig|
|DomainName|String|Yes.|www.macaron.org.cn|Your CDN domain name.|
|RedirectType|String|Yes.|Off| Force redirect type.  Value:

 -   Off
-   Http
-   Https

 |

## Return parameters {#section_elq_cdg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetForceRedirectConfig
&DomainName=www.macaron.org.cn
&RedirectType=Https
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
        "Requestid": "maid"
    
    ```


