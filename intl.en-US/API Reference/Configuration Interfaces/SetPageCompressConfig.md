# SetPageCompressConfig {#reference_yrq_4wf_vdb .reference}

Set the smart compression function.

## Request parameters {#section_fcm_qwf_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetPageCompressConfig|The name of this interface.  Value: SetPageCompressConfig|
|DomainName|String|Yes|www.macaron.org.cn|Your CDN domain which needs smart compression configuration.|
|Enable|String|Yes|On| Enable or disable the smart compression function. 

 Value: On, Off

 |

## Return parameters {#section_x3h_5wf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_dlv_wwf_vdb .section}

**Request example**

```
http://cdn.aliyuncs.com/?Action=SetPageCompressConfig&Enable=on&DomainName=www.macaron.org.cn&Public request parameter
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


