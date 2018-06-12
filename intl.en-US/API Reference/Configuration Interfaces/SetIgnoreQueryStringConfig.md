# SetIgnoreQueryStringConfig {#reference_akk_gxf_vdb .reference}

Set the filter parameter function.

## Request parameters {#section_jtt_hxf_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetIgnoreQueryStringConfig|The name of this interface.  Value: SetIgnoreQueryStringConfig|
|DomainName|String|Yes|www.macaron.org.cn|Your CDN domain name which needs enabling the filter parameter function.|
|Enable|String|Yes|On|Enable or disable the filter parameter function. Value: On, Off|
|HashKeyArgs|String|No|time|Retention parameters. Multiple retention parameters are separated by comma \(English, half-width\), and at most 10 retention parameters are configured.|
|KeepOssArgs|String|No|On| Value: On, Off

 -   On: indicates all the parameters are retained in the process of back-to-source.
-   Off: indicates being disabled.

 |

## Return parameters {#section_l3y_pxf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_d3w_rxf_vdb .section}

**Request example**

```
http://cdn.aliyuncs.com/?Action=SetIgnoreQueryStringConfig&Enable=on&DomainName=www.macaron.org.cn&Public request parameter
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


