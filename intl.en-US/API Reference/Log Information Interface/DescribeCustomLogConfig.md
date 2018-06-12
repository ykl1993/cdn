# DescribeCustomLogConfig {#reference_iwf_qf2_vdb .reference}

Query custom log configuration details according to configId.

## Request parameters {#section_r3h_nr2_vdb .section}

|Parameters|Type| Required| Example values|Description|
|Action|String|Yes|DescribeCustomLogConfig|The name of this interface. Value: DescribeCustomLogConfig|
|ConfigId|String|Yes|123|Custom configuration ID.|
|Version|String|No|2014-11-11|API version.|

## Return parameters {#section_grl_vr2_vdb .section}

|Parameters|Type| Example values| Description|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The request ID.|
|Remark|String|$timeiso8601$requestmethod$|Detailed configuration format.|
|Sample|String|“\[9/Jun/2015:01:58:09 +0800\] 188.165.15.75 - 1542 \\”-\\” \\”GEThttp: //www.aliyun.com/index.html\\” 200|Example.|
|Tag|String|Img1|Tag information of log configuration.|

## Example {#section_jyr_zr2_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com? https://cdn.aliyuncs.com?Action=DescribeCustomLogConfig?ConfigId=2df93fd7-5bbc-48c0-bae2-1ee1032d8d86<public request parameter>
```

**Normal return example**

-   JSON format

    ```
    
        "Remark":"$time_iso8601_$request_method_$server_protocol.....",
        "RequestId":"F32C57AA-7BF8-49AE-A2CC-3F42390F5A16",
        "Sample":"[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 \"-\" \"GEThttp: //www.aliyun.com/index.html\" 200",
        "Tag":"xxxxx"
    
    ```


**Exception return exmaple**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


