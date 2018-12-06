# SetIgnoreQueryStringConfig {#reference_akk_gxf_vdb .reference}

设置过滤参数功能。

## 请求参数 {#section_jtt_hxf_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetIgnoreQueryStringConfig|系统规定参数。取值：SetIgnoreQueryStringConfig|
|DomainName|String|是|www.macaron.org.cn|要开启该功能的加速域名。|
|Enable|String|是|On|配置过滤参数功能的开启或关闭。取值：On、Off|
|HashKeyArgs|String|否|time|保留参数，多个用逗号（英文、半角）分隔，最多配置10个保留参数。|
|KeepOssArgs|String|否|on| 取值：On、Off。

 -   On：表示回源保留所有参数。
-   Off：表示关闭。

 |

## 返回参数 {#section_l3y_pxf_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_d3w_rxf_vdb .section}

**请求示例**

```
http://cdn.aliyuncs.com/?Action=SetIgnoreQueryStringConfig&Enable=on&DomainName=www.macaron.org.cn&公共请求参数
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


