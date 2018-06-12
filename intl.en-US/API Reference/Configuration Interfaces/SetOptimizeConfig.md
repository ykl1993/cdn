# SetOptimizeConfig {#reference_ar2_cvf_vdb .reference}

The page optimization function can be used to delete comments and repeated white spaces embedded in HTML, Javascript and CSS   to effectively remove redundant page content, reduce the file size, and improve the efficiency of accelerated delivery.

## Request parameters {#section_awn_fvf_vdb .section}

|Name|Type|Required|Example values|Description|
|Action|String|Yes|SetOptimizeConfig|The name of this interface.  Value: SetOptimizeConfig|
|DomainName|String|Yes|www.macaron.org.cn|The CDN domain name which needs the page optimization function.|
|Enable|String|Yes|On| Enable or disable the page optimization function. 

 Value: On, Off

 |

## Return parameters {#section_krq_qvf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_sgh_cwf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetOptimizeConfig
&Enable=on
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

