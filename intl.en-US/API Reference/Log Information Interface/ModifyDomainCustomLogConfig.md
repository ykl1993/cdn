# ModifyDomainCustomLogConfig {#reference_jcb_vs2_vdb .reference}

Modify custom log configurations under a domain name.

## Request parameters {#section_m3r_ws2_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainCustomLogConfig|The name of this interface. Value: ModifyDomainCustomLogConfig|
|DomainName|String|Yes|www.yourdomain.com|Domain name.|
|Version|String|No|2014-11-11|API version.|

## Return Parameters {#section_njz_wgf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request.|
|Configid|String|123|Log configuration ID.|
|Mark|String|$timeiso8601$requestmethod$|Specific configuration format.|
|Sample|String|\[9/Jun/2015:01:58:09+0800\]188.165.15.75-1542\\”-\\”\\”GET [http://www.aliyun.com/index.html\\](http://www.aliyun.com/index.html/)|Sample.|
|Tag|String|Book|Log configuration ID.|

## Examples {#section_sr4_chf_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=DescribeDomainCustomLogConfig&DomainName=xxxx.comPublic request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "ConfigId":"25473b84-d598-498e-b148-f23d0a27df52",
        "Remark":"$time_iso8601_$request_method_$server_protocol.....",
        "Requestid": "maid ",
        "Sample":"[9/Jun/2015:01:58:09+0800]188.165.15.75-1542\"-\"\"GET http://www.aliyun.com/index.html\"2001912830MISS\"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)",
        "Tag":"xxxxx"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


