# SetVideoSeekConfig {#reference_hpt_yzf_vdb .reference}

设置拖拽播放功能。

**说明：** 

-   需要源站支持range请求，即对于http请求头中包含Range字段，源站能够响应正确的206文件分片。
-   目前支持文件格式有：MP4和FLV。

## 请求参数 {#section_vlp_g1g_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetVideoSeekConfig|系统规定参数。取值：SetVideoSeekConfig|
|DomainName|String|是|www.macaron.org.cn|加速域名。|
|Enable|String|是|On|配置拖拽播放功能的开启或关闭。取值：On、Off|

## 返回参数 {#section_zvm_j1g_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_z2b_l1g_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetVideoSeekConfig
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


