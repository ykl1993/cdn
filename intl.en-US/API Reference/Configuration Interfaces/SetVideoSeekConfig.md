# SetVideoSeekConfig {#reference_hpt_yzf_vdb .reference}

Set the drag/drop playback function.

**Note:** 

-   To use the range back-to-source function, ensure that the source site supports Range requests, indicating that the source site must be able to return correct 206 partial content for an HTTP request header containing a Range field.
-   Currently, the MP4 and FLV file formats are supported.

## Request parameters {#section_vlp_g1g_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetVideoSeekConfig|The name of this interface.  Value: SetVideoSeekConfig|
|DomainName|String|Yes.|www.macaron.org.cn|Your CDN domain name.|
|Enable|String|Yes.|On|Enable or disable the drag/drop playback function.  Value: On, off|

## Return parameters {#section_zvm_j1g_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_z2b_l1g_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetVideoSeekConfig
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


