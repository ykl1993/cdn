# DescribeDomainMax95BpsData {#reference_in2_bgn_vdb .reference}

获取加速域名95带宽峰值监控数据。单位：bit/second。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 请求参数 {#section_kcl_5hn_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainMax95BpsData|系统规定参数。取值：DescribeDomainMax95BpsData|
|DomainName|String|否|www.yourdomain.com| 若参数为空，默认返回所有加速域名合并后数据。

 -   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z| 获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#section_as2_b3n_vdb .section}

|参数|类型|示例值|描述|
|DomainName|String|test.com|加速域名信息。|
|StartTime|String|2015-12-10T20:00Z|开始时间。|
|EndTime|String|2015-12-10T21:00Z|结束时间。|
|Max95Bps|String|16777590.28|95带宽峰值。|
|DomesticMax95Bps|String|16777590.28|国内95带宽峰值。|
|OverseasMax95Bps|String|0|海外95带宽峰值。|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainMax95BpsData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DomainName":"test.com",
        "DomesticMax95Bps":"16777590.28",
        "EndTime":"2015-12-10T21:00Z",
        "Max95Bps":"16777590.28",
        "OverseasMax95Bps":"0",
        "RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
        "StartTime":"2015-12-10T20:00Z"
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


