# DescribeDomainCustomLogConfig {#reference_jcb_vs2_vdb .reference}

获取域名自定义日志格式配置信息。

## 请求参数 {#section_m3r_ws2_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainCustomLogConfig|系统规定参数。取值：DescribeDomainCustomLogConfig|
|DomainName|String|是|www.yourdomain.com|域名（只支持单个查询）。|
|Version|String|否|2014-11-11|API版本号。|

## 返回参数 {#section_njz_wgf_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。|
|ConfigId|String|123|日志配置ID。|
|Remark|String|$timeiso8601$requestmethod$|具体配置格式。|
|Sample|String|\[9/Jun/2015:01:58:09+0800\]188.165.15.75-1542\\”-\\”\\”GET [http://www.aliyun.com/index.html\\](http://www.aliyun.com/index.html/)|样例。|
|Tag|String|book|日志配置tag信息。|

## 示例 {#section_sr4_chf_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?Action=DescribeDomainCustomLogConfig&DomainName=xxxx.com公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "ConfigId":"25473b84-d598-498e-b148-f23d0a27df52",
        "Remark":"$time_iso8601_$request_method_$server_protocol.....",
        "RequestId":"1805F349-0A2B-41D9-B4AD-33632AFC27F1",
        "Sample":"[9/Jun/2015:01:58:09+0800]188.165.15.75-1542\"-\"\"GET http://www.aliyun.com/index.html\"2001912830MISS\"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)",
        "Tag":"xxxxx"
    }
    ```


**异常返回示例**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```


