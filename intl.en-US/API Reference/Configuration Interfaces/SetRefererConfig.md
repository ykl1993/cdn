# SetRefererConfig {#reference_bf3_kdg_vdb .reference}

Set the referer anti-leech function for CDN domain names.

## Request parameters {#section_cfq_mdg_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetRefererConfig|The name of this interface.  Value: SetRefererConfig|
|DomainName|String|Yes.|www.yourdomain.com|Your CDN domain name.|
|ReferType|String|Yes.|block| Refer type.  Value:

 -   block: blacklist 
-   allow: whitelist

 |
|AllowEmpty|String|No|on|Whether to allow access with a blank referer.  Value:

 -   on: allowed
-   off: not allowed

 Default value: on|
|DisableAst|String|No|off|Whether CDN domain name is matched exactly. Value:

 -   on: exact match, not automatically match the sub-domain-name.
-   off: fuzzy match, automatically match the sub-domain-name.

 Default value: off|
|ReferList|String|No|a.com,b.com|The domain name lists separated by comma \(,\).|

## Return parameters {#section_asb_pdg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetRefererConfig
&DomainName=www.macaron.org.cn
&ReferList=www.aliyun.com%2Cwww.taobao.com
&ReferType=allow
&AllowEmpty=on
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


