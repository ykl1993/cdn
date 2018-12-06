# DescribeCustomLogConfig {#reference_iwf_qf2_vdb .reference}

根据configId查询自定义日志配置详细信息。

## 请求参数 {#section_r3h_nr2_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeCustomLogConfig|系统规定参数。取值：DescribeCustomLogConfig|
|ConfigId|String|是|123|自定义配置ID。|
|Version|String|否|2014-11-11|API版本号。|

## 返回参数 {#section_grl_vr2_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。|
|Remark|String|$timeiso8601$requestmethod$|具体配置格式。|
|Sample|String|“\[9/Jun/2015:01:58:09 +0800\] 188.165.15.75 - 1542 \\”-\\” \\”GEThttp: //www.aliyun.com/index.html\\” 200|样例。|
|Tag|String|img1|日志配置tag信息。|

## 示例 {#section_jyr_zr2_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?Action=DescribeCustomLogConfig?ConfigId=2df93fd7-5bbc-48c0-bae2-1ee1032d8d86公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "Remark":"$time_iso8601_$request_method_$server_protocol.....",
        "RequestId":"F32C57AA-7BF8-49AE-A2CC-3F42390F5A16",
        "Sample":"[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 \"-\" \"GEThttp: //www.aliyun.com/index.html\" 200",
        "Tag":"xxxxx"
    }
    ```


**异常返回格式**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```


