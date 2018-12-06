# SetIpBlackListConfig {#reference_qwx_2kl_vdb .reference}

设置加速域名的IP黑名单。

**说明：** IP黑名单当前支持ip网段添加。 例如：127.0.0.1/24，24表示采用子网掩码中的前24位为有效位，即用32-24=8bit来表示主机号，该子网可以容纳2^8 - 2 = 254 台主机。故127.0.0.1/24 表示IP网段范围是：127.0.0.1~127.0.0.255。

## 请求参数 {#section_ekn_jkl_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetIpBlackListConfig|系统规定参数。取值：SetIpBlackListConfig|
|BlockIps|String|是|192.168.0.1|IP黑名单，表示此IP列表禁止访问，IP列表多个用逗号隔开。|
|DomainName|String|是|www.macaron.org.cn|您的加速域名。|

## 返回参数 {#section_uzx_lkl_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetIpBlackListConfig
&DomainName=www.macaron.org.cn
&BlockIps=192.168.0.1%2F24
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


