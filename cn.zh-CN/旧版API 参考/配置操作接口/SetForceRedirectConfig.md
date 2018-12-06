# SetForceRedirectConfig {#reference_qvw_ncg_vdb .reference}

设置强制访问跳转方式，目前支持强制Http或Https跳转。

**说明：** 只有已经上传证书，且证书被启用的情况下，才能打开强制跳转功能。

## 请求参数 {#section_b1s_vcg_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetForceRedirectConfig|系统规定参数。取值：SetForceRedirectConfig|
|DomainName|String|是|www.macaron.org.cn|加速域名。|
|RedirectType|String|是|Off| 强制跳转类型。取值:

 -   Off
-   Http
-   Https

 |

## 返回参数 {#section_elq_cdg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetForceRedirectConfig
&DomainName=www.macaron.org.cn
&RedirectType=Https
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


