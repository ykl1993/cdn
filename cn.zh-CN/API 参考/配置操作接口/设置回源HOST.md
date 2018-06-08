# 设置回源HOST {#reference_pfj_s1g_vdb .reference}

设置回源host功能。

**说明：** 若源站为OSS域名，需将OSS域名设置为回源host（即源站域名），方可正常回源。

## 请求参数 {#section_rwc_51g_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetSourceHostConfig|系统规定参数。取值：SetSourceHostConfig|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|BackSrcDomain|String|否|www.aliyun.com|自定义回源域名。|
|Enable|String|否|On| 枚举on，off。是否打开自定义host配置。

 默认值：on

 |

## 返回参数 {#section_nz2_1bg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_tbx_bbg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetSourceHostConfig
&BackSrcDomain=www.aliyun.com
&DomainName=www.macaron.org.cn
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
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


