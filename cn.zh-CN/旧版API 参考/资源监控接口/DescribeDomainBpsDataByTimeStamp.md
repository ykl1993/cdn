# DescribeDomainBpsDataByTimeStamp {#reference_fzq_lfn_vdb .reference}

获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位 bit/second。

-   不支持批量域名查询。
-   时间精确到5分钟粒度。

## 请求参数 {#section_pzz_pfn_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainBpsDataByTimeStamp|系统规定参数。取值：DescribeDomainBpsDataByTimeStamp|
|DomainName|String|是|www.yourdomain.com|要查询的域名，不能为空。|
|IspNames|String|是|unicom,telecom| 需要查询目标Isp列表，用“,”隔开，不能为空。

 ISP名通过DescribeCdnRegionAndIsp接口获得。

 |
|LocationNames|String|是|liaoning,guangxi| 需要查询目标区域列表，用“,”隔开，不能为空。

 Location名通过DescribeCdnRegionAndIsp接口获得。

 |
|TimePoint|String|是|2016-08-01T22:00Z| 查询目标时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |

## 返回参数 {#section_ffh_vfn_vdb .section}

|参数|类型|示例值|描述|
|DomainName|String|abc.cn|加速域名信息。|
|BpsDataList| | |每个Locate、ISP对应的bps值。|
|  └LocationName|String|Liaoning|节点名。|
|  └IspName|String|unicom|Isp名。|
|  └Bps|Long|52119553|对应的带宽值。|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|
|TimeStamp|String|2017-12-22T08:00:00:00Z|时刻。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByTimeStamp&DomainName=abc.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&TimePoint=2016-08-01T22:00Z
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "BpsDataList":{
            "BpsDataModel":[
                {
                    "Bps":880996111,
                    "IspName":"telecom",
                    "LocationName":"Liaoning"
                },
                {
                    "Bps":52119553,
                    "IspName":"unicom",
                    "LocationName":"Liaoning"
                },
                {
                    "Bps":51295137,
                    "IspName":"telecom",
                    "LocationName":"Guangxi"
                },
                {
                    "Bps":18673571,
                    "IspName":"unicom",
                    "LocationName":"Guangxi"
                }
            ]
        },
        "DomainName":"abc.cn",
        "RequestId":"7682DE14-3B4D-48D0-9B7C-DD3C8C3E1C78",
        "TimeStamp":"2016-08-01T22:00Z"
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


