# SetSourceHostConfig {#reference_pfj_s1g_vdb .reference}

Set the back-to-source host function.

**Note:** If the origin site is an OSS domain name, the OSS domain name must be set as the back-to-source host \(that is, the source site domain name\) to ensure normal back-to-source operation.

## Request parameters {#section_rwc_51g_vdb .section}

|Parameters|Type|Required|Example value|Description|
|Action|String|Yes|Setsourcehostconfig|The name of this interface. Value: SetSourceHostConfig|
|DomainName|String|Yes|www.yourdomain.com|Your CDN domain name.|
|BackSrcDomain|String|No|www.aliyun.com|Custom back-to-source domain name.|
|Enable|String|No|On| Enum on, off. Whether the custom host configuration is enabled. 

 Default value: on

 |

## Return parameters {#section_nz2_1bg_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_tbx_bbg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetSourceHostConfig
&BackSrcDomain=www.aliyun.com
&DomainName=www.macaron.org.cn
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


