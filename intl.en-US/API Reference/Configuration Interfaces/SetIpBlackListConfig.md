# SetIpBlackListConfig {#reference_qwx_2kl_vdb .reference}

Sets the IP address blacklist of a CDN domain.

**Note:** You can add an IP address segment to the blacklist.  For example, 127.0.0.1/24.In 127.0.0.1/24, “24” indicates that the first 24 bits in the subnet mask are used as valid bits. That is, 32 - 24 = 8 bits are used to express the host number. In this way, the subnet can accommodate 2 ^ 8 - 2 = 254 Hosts.  The IP address segment range of “127.0.0.1/24” is 127.0.0.1 - 127.0.0.255.

## Request parameters {#section_ekn_jkl_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetIpBlackListConfig|The name of this interface.  Value: SetIpBlackListConfig|
|BlockIps|String|Yes.|192.168.0.1|IP address blacklist. Access by the listed IP addresses is forbidden. Multiple IP addresses are separated by commas \(,\).|
|DomainName|String|Yes.|www.macaron.org.cn|Your CDN domain name.|

## Return parameters {#section_uzx_lkl_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetIpBlackListConfig
&DomainName=www.macaron.org.cn
&BlockIps=192.168.0.1%2F24
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


