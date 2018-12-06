# DescribeDomainRealTimeBpsData {#reference_aqm_kns_vdb .reference}

获取域名1分钟粒度带宽数据。

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。

## 请求参数 {#section_ngq_qns_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainRealTimeBpsData|系统规定参数。取值：DescribeDomainRealTimeBpsData|
|DomainName|String|是|test.test.com|加速域名。|
|EndTime|String|否|2016-10-20T04:00:00Z| 结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从StartTime起一小时内的数据。

 |
|IspNameEn|String|否|telecom|运营商英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有运营商。|
|LocationNameEn|String|否|beijing|区域英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有区域。|
|StartTime|String|否|2016-10-20T04:00:00Z| 起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从EndTime起一小时内的数据。

 |
|Version|String|否|2014-11-11|API版本。|

## 返回参数 {#section_btb_tns_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|B49E6DDA-F413-422B-B58E-2FA23F286726|请求ID。|
|Data| | |返回数据。|
|  └Bps|Float|16710625.733333332| 带宽数据。

 单位：bit/second

 |
|  └TimeStamp|String|2018-01-02T11:04:00Z| 数据时间戳。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

**请求参数****返回参数**

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeBpsData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Z&IspNameEn=telecom&LocationNameEn=beijing公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "Data":{
            "BpsModel":[
                {
                    "Bps":16710625.733333332,
                    "TimeStamp":"2018-01-02T11:05:00Z"
                },
                {
                    "Bps":59392614.8,
                    "TimeStamp":"2018-01-02T11:04:00Z"
                }
            ]
        },
        "RequestId":"B49E6DDA-F413-422B-B58E-2FA23F286726"
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


