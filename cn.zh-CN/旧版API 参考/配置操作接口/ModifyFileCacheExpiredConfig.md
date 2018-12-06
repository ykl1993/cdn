# ModifyFileCacheExpiredConfig {#reference_l5v_dgg_vdb .reference}

修改文件过期配置。

## 请求参数 {#section_mzs_fgg_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|ModifyFileCacheExpiredConfig|系统规定参数。取值：ModifyFileCacheExpiredConfig|
|CacheContent|String|是|jpg,png|填写文件名后缀，逗号分隔。|
|ConfigID|String|是|905535|要修改的配置ID。|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|TTL|String|是|600| 缓存时间设置。

 单位：秒

 |
|Weight|String|否|22| 此条配置的权重值。取值范围：1-99。数值越大，优先级越高。

 默认值：1

 |

## 返回参数 {#section_efp_jgg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=ModifyFileCacheExpiredConfig
&CacheContent=jpg%2Cpng
&DomainName=www.macaron.org.cn
&TTL=600
&Weight=50
&ConfigID=905535
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


