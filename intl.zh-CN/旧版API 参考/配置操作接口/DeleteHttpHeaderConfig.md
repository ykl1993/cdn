# DeleteHttpHeaderConfig {#reference_sq1_fjl_vdb .reference}

删除加速域名的Referer防盗链配置。

## 请求参数 {#section_eqx_gjl_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DeleteHttpHeaderConfig|系统规定参数。取值：DeleteHttpHeaderConfig|
|ConfigID|String|是|438205|配置ID。|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|

## 返回参数 {#section_f11_jjl_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=DeleteHttpHeaderConfig
&DomainName=www.macaron.org.cn
&ConfigID=438205
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


