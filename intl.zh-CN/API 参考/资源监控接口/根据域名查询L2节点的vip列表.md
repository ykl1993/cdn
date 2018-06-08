# 根据域名查询L2节点的vip列表 {#reference_nhk_gjn_vdb .reference}

按域名查询L2节点vip列表。配置白名单后才可以生效。

**说明：** 

-   支持日峰值带宽为 1Gbps 以上的用户提工单申请该接口的调用权限。单击[立即申请](https://workorder.console.aliyun.com/console.htm?lang=#/ticket/add?productCode=cdn)。
-   使用场景介绍，参见 [CDN的回源地址有哪些？](https://help.aliyun.com/document_detail/40205.html)

## 请求参数 {#section_km5_h4n_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeL2VipsByDomain|系统规定参数。取值：DescribeL2VipsByDomain|
|DomainName|String|是|www.yourdomain.com| 域名。

 取值范围： 只支持单个域名，需加白名单。

 |

## 返回参数 {#section_hyx_l4n_vdb .section}

|参数|类型|示例值|描述|
|DomainName|String|xxxx.com|域名。|
|Vips|String|“Vip”: \[ “1.1.1.1/25”, “2.2.2.2/25” \]|Vip列表。|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain&DomainName=xxxx.com&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DomainName":"xxxx.com",
        "RequestId":"820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
        "Vips":{
            "Vip":[
                "1.1.1.1/25",
                "2.2.2.2/25"
            ]
        }
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


