# 设置Range回源 {#reference_h13_2yf_vdb .reference}

设置range回源功能。

**说明：** 需要源站支持range请求，即对于http请求头中包含 Range 字段，源站能够响应正确的206文件分片。

## 请求参数 {#section_slq_3yf_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetRangeConfig|系统规定参数。取值：SetRangeConfig|
|DomainName|String|是|www.macaron.org.cn|要开启该功能的加速域名。|
|Enable|String|是|On| 配置range回源功能的开启或关闭。

 取值：On、Off

 |

## 返回参数 {#section_xbc_lyf_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_pg5_myf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetRangeConfig
&Enable=on
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


