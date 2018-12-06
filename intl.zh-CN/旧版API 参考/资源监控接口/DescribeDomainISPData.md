# DescribeDomainISPData {#reference_lhj_pzm_vdb .reference}

获取加速域名天粒度的 用户运营商分布数据统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 请求参数 {#section_s4r_tzm_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainISPData|系统规定参数。取值：DescribeDomainISPData|
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|EndTime|String|否|2015-12-05| -   结束时间需大于起始时间，北京时间。
-   格式为：YYYY-MM-DD。

 |
|startTime|String|否|2015-12-05| -   获取数据起始时间点，北京时间。
-   格式为：YYYY-MM-DD。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#section_x1z_zzm_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|DE81639B-DAC1-4C76-AB72-F34B836837D5|请求ID。|
|DomainName|String|test.test.com|加速域名。|
|DataInterval|String|86400|时间间隔。|
|StartTime|String|2016-03-14|获取数据起始时间点。|
|EndTime|String|2016-03-14|获取数据结束时间点。|
|Value| | |各运营商访问占比数据list。|
|  └ISP|String|阿里巴巴|运营商信息。|
|  └Proportion|String|0.004509176173513099|占比使用数据。|
|  └IspEname|String|alibaba|运营商英文名称。|
|  └AvgObjectSize|String|7081884.7|响应平均大小。单位：byte。|
|  └AvgResponseTime|String|79638.0|平均响应时间。单位：毫秒。|
|  └Bps|String|1311.4601296296296|带宽。|
|  └ByteHitRate|String|100.0|字节命中率。|
|  └Qps|String|2.3148148148148147E-5|每秒查询率。|
|  └ReqErrRate|String|0.0|请求错误率。|
|  └ReqHitRate|String|100.0|命中。|
|  └AvgResponseRate|String|88.92594866772144|平均响应速度。单位：byte/毫秒。|
|  └TotalBytes|String|7081884|总流量。|
|  └BytesProportion|String|0.012220518530445479|总流量占比。|
|  └TotalQuery|String|1|总请求次数。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainISPData&DomainName=test.com
&StartTime=2015-12-05
&EndTime=2015-12-07
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DataInterval":"86400",
        "DomainName":"downtest.cdnpe.com",
        "EndTime":"2016-03-14",
        "RequestId":"DE81639B-DAC1-4C76-AB72-F34B836837D5",
        "StartTime":"2016-03-13",
        "Value":{
            "ISPProportionData":[
                {
                    "AvgObjectSize":"7081884.7",
                    "AvgResponseRate":"88.92594866772144",
                    "AvgResponseTime":"79638.0",
                    "Bps":"1311.4601296296296",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.012220518530445479",
                    "ISP":"阿里巴巴",
                    "IspEname":"alibaba",
                    "Proportion":"0.004509176173513099",
                    "Qps":"2.3148148148148147E-5",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"7081884",
                    "TotalQuery":"1"
                },
                {
                    "AvgObjectSize":"800019.0",
                    "AvgResponseRate":"154.3345765545624",
                    "AvgResponseTime":"5183.666666666667",
                    "Bps":"444.455",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.004141544558417533",
                    "ISP":"海外ISP",
                    "IspEname":"overseas",
                    "Proportion":"0.013527528520539298",
                    "Qps":"6.944444444444444E-5",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2400057",
                    "TotalQuery":"3"
                },
                {
                    "AvgObjectSize":"3018642.684146342",
                    "AvgResponseRate":"1025.5028528460102",
                    "AvgResponseTime":"2943.5731707317073",
                    "Bps":"45838.64816666667",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.42713616424581613",
                    "ISP":"鹏博士",
                    "IspEname":"drpeng",
                    "Proportion":"0.3697524462280741",
                    "Qps":"0.0018981481481481482",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"247528700",
                    "TotalQuery":"82"
                },
                {
                    "AvgObjectSize":"3123166.4508771934",
                    "AvgResponseRate":"484.6396117340071",
                    "AvgResponseTime":"6444.30701754386",
                    "Bps":"65933.51396296297",
                    "ByteHitRate":"99.99999999999999",
                    "BytesProportion":"0.6143852267848392",
                    "ISP":"教育网",
                    "IspEname":"cernet",
                    "Proportion":"0.5140460837804933",
                    "Qps":"0.002638888888888889",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"356040975",
                    "TotalQuery":"114"
                },
                {
                    "AvgObjectSize":"2116401.843961353",
                    "AvgResponseRate":"752.2096624205244",
                    "AvgResponseTime":"2813.5797101449275",
                    "Bps":"81128.73735185186",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.7559781771177001",
                    "ISP":"铁通",
                    "IspEname":"tietong",
                    "Proportion":"0.9333994679172115",
                    "Qps":"0.004791666666666666",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"438095181",
                    "TotalQuery":"207"
                },
                {
                    "AvgObjectSize":"2723991.4195312504",
                    "AvgResponseRate":"321.5924922592767",
                    "AvgResponseTime":"8470.3203125",
                    "Bps":"129137.37100000001",
                    "ByteHitRate":"100.00000000000001",
                    "BytesProportion":"1.2033348171432345",
                    "ISP":"其他",
                    "IspEname":"other",
                    "Proportion":"1.1543491004193533",
                    "Qps":"0.005925925925925926",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"697341803",
                    "TotalQuery":"256"
                },
                {
                    "AvgObjectSize":"1657975.598360084",
                    "AvgResponseRate":"1004.5513789924338",
                    "AvgResponseTime":"1650.463712491277",
                    "Bps":"879955.1972037038",
                    "ByteHitRate":"99.14745652563326",
                    "BytesProportion":"8.19964599032574",
                    "ISP":"移动",
                    "IspEname":"mobile",
                    "Proportion":"12.923298913288543",
                    "Qps":"0.06634259259259259",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"97.3831123517097",
                    "TotalBytes":"4751758064",
                    "TotalQuery":"2866"
                },
                {
                    "AvgObjectSize":"2640215.374074074",
                    "AvgResponseRate":"1171.525957981939",
                    "AvgResponseTime":"2253.6550352004897",
                    "Bps":"3194660.60262963",
                    "ByteHitRate":"99.99981717005271",
                    "BytesProportion":"29.768658772680293",
                    "ISP":"联通",
                    "IspEname":"unicom",
                    "Proportion":"29.46295711773459",
                    "Qps":"0.15125",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.96939087848179",
                    "TotalBytes":"17251167254",
                    "TotalQuery":"6534"
                },
                {
                    "AvgObjectSize":"2823126.71357933",
                    "AvgResponseRate":"984.184264638081",
                    "AvgResponseTime":"2868.494056463596",
                    "Bps":"6333214.260796296",
                    "ByteHitRate":"99.99968869093071",
                    "BytesProportion":"59.01449878861353",
                    "ISP":"电信",
                    "IspEname":"telecom",
                    "Proportion":"54.62416016593768",
                    "Qps":"0.28041666666666665",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.97523526498266",
                    "TotalBytes":"34199357008",
                    "TotalQuery":"12114"
                }
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


