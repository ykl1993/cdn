# DescribeDomainRealTimeQpsData {#reference_jy2_sqs_vdb .reference}

获取域名1分钟粒度每秒访问次数数据。

-   您可以查询7天内的数据。单次查询StartTime和EndTime跨度不能超过24小时。
-   如果您未指定StartTime和EndTime，则系统默认返回当前时间起一小时内的数据。

## 请求参数 {#section_nml_kxs_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainRealTimeQpsData|系统规定参数。取值：DescribeDomainRealTimeQpsData|
|DomainName|String|是|test.test.com|加速域名。|
|EndTime|String|否|2016-10-20T04:00:00Z| 结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   不填默认查询从EndTime起一小时内的数据。

 |
|IspNameEn|String|否|telecom|运营商英文名，通过DescribeCdnRegionAndIsp接口获得。如果不传，则默认为所有运营商。|
|LocationNameEn|String|否|beijing|区域英文名，通过DescribeCdnRegionAndIsp接口获得。如果不传，则默认为所有区域。|
|StartTime|String|否|2016-10-20T04:00:00Z| 起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   不填默认查询从EndTime起一小时内的数据。

 |
|Version|String|否|2014-11-11|API版本。|

## 返回参数 {#section_nfh_kys_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D|请求ID。|
|Data|String| |返回数据。|
|  └Qps|Float|1851.25|QPS数据。|
|  └TimeStamp|String|2018-01-02T11:26:00Z|数据时间戳。

日期格式按照ISO8601表示法，并使用UTC时间。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeQpsData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Z&IspNameEn=telecom&LocationNameEn=beijing公共请求参数
```

**正常返回示例**

JSON格式

```
{
    "Data":{
        "QpsModel":[
            {
                "Qps":1851.25,
                "TimeStamp":"2018-01-02T11:26:00Z"
            },
            {
                "Qps":8967.7,
                "TimeStamp":"2018-01-02T11:25:00Z"
            }
        ]
    },
    "RequestId":"32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
}
```

**异常返回示例**

JSON格式

```
{
    "Code":"InternalError",
    "HostId":"cdn.aliyuncs.com",
    "Message":"The request processing has failed due to some unknown error.",
    "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
}
```

