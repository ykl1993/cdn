# 查询域名的PV页面访问统计 {#reference_tvd_lxm_vdb .reference}

获取加速域名最小1小时粒度的 PV页面访问统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 请求参数 {#section_o2w_qxm_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainPvData|系统规定参数。取值：DescribeDomainPvData|
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|EndTime|String|否|2015-11-29| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|StartTime|String|否|2015-11-28| -   获取数据起始时间点。
-   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#section_sg3_wxm_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|BCD7D917-76F1-442F-BB75-C810DE34C761|请求ID。|
|DomainName|String|test.test.com|加速域名。|
|DataInterval|String|3600|时间间隔。|
|StartTime|String|2015-11-28| 获取数据起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。

 |
|EndTime|String|2015-11-29|获取数据结束时间。|
|PvDataInterval| | |数据。|
|  └TimeStamp|String|2015-11-28T03:00:00Z|时间戳。|
|  └Value|String|9292|数值。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainPvData&DomainName=test.com
&StartTime=2015-11-28
&EndTime=2015-11-29
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":"3600",
        "DomainName":"test.com",
        "EndTime":"2015-11-29",
        "PvDataInterval":{
            "UsageData":[
                {
                    "TimeStamp":"2015-11-28T03:00:00Z",
                    "Value":"9292"
                },
                {
                    "TimeStamp":"2015-11-28T23:00:00Z",
                    "Value":"9239"
                },
                {
                    "TimeStamp":"2015-11-28T07:00:00Z",
                    "Value":"9464"
                },
                {
                    "TimeStamp":"2015-11-28T12:00:00Z",
                    "Value":"9379"
                },
                {
                    "TimeStamp":"2015-11-28T22:00:00Z",
                    "Value":"9243"
                },
                {
                    "TimeStamp":"2015-11-28T10:00:00Z",
                    "Value":"10063"
                },
                {
                    "TimeStamp":"2015-11-28T15:00:00Z",
                    "Value":"9068"
                },
                {
                    "TimeStamp":"2015-11-28T14:00:00Z",
                    "Value":"9353"
                },
                {
                    "TimeStamp":"2015-11-28T04:00:00Z",
                    "Value":"9513"
                },
                {
                    "TimeStamp":"2015-11-28T02:00:00Z",
                    "Value":"9377"
                },
                {
                    "TimeStamp":"2015-11-28T08:00:00Z",
                    "Value":"9579"
                },
                {
                    "TimeStamp":"2015-11-28T20:00:00Z",
                    "Value":"9109"
                },
                {
                    "TimeStamp":"2015-11-28T09:00:00Z",
                    "Value":"10631"
                },
                {
                    "TimeStamp":"2015-11-28T06:00:00Z",
                    "Value":"9587"
                },
                {
                    "TimeStamp":"2015-11-28T01:00:00Z",
                    "Value":"9108"
                },
                {
                    "TimeStamp":"2015-11-28T16:00:00Z",
                    "Value":"9454"
                },
                {
                    "TimeStamp":"2015-11-28T21:00:00Z",
                    "Value":"9285"
                },
                {
                    "TimeStamp":"2015-11-28T19:00:00Z",
                    "Value":"9059"
                },
                {
                    "TimeStamp":"2015-11-28T00:00:00Z",
                    "Value":"9470"
                },
                {
                    "TimeStamp":"2015-11-28T05:00:00Z",
                    "Value":"11830"
                },
                {
                    "TimeStamp":"2015-11-28T13:00:00Z",
                    "Value":"9992"
                },
                {
                    "TimeStamp":"2015-11-28T17:00:00Z",
                    "Value":"9529"
                },
                {
                    "TimeStamp":"2015-11-28T18:00:00Z",
                    "Value":"9203"
                },
                {
                    "TimeStamp":"2015-11-28T11:00:00Z",
                    "Value":"9604"
                }
            ]
        },
        "RequestId":"BCD7D917-76F1-442F-BB75-C810DE34C761",
        "StartTime":"2015-11-28"
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


