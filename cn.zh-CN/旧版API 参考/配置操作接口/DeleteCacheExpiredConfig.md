# DeleteCacheExpiredConfig {#reference_dvq_53g_vdb .reference}

删除自定义缓存策略。

## 请求参数 {#section_xjc_mjg_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DeleteCacheExpiredConfig|系统规定参数。取值：DeleteCacheExpiredConfig|
|CacheType|String|是|suffix| 缓存内容类型。取值：

 -   suffix：文件名后缀
-   path：路径，支持目录和完整路径

 |
|ConfigID|String|是|903423|配置ID，新增时不需要指定，修改需要指定。|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|

## 返回参数 {#section_ntd_gxg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=DeleteCacheExpiredConfig
&CacheType=path
&ConfigID=903423
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


