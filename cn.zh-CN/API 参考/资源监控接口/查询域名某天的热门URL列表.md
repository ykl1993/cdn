# 查询域名某天的热门URL列表 {#reference_ddf_g1n_vdb .reference}

获取加速域名某天内的热门URL列表。

-   不指定StartTime，默认读取前一天的数据。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 请求参数 {#section_hd5_t1n_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainTopUrlVisit|系统规定参数。取值：DescribeDomainTopUrlVisit|
|DomainName|String|否|test.test.com|只支持一个域名，若参数为空，默认返回所有加速域名合并后数据。|
|SortBy|String|否|pv| 排序方式。

 -   支持traf和pv。
-   默认值：pv

 |
|StartTime|String|否|2015-12-03| 获取数据起始时间点，北京时间。

 -   格式为：YYYY-MM-DD。
-   不写默认读取过去24小时数据。

 |

## 返回参数 {#section_nqf_v1n_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID。|
|DomainName|String|test.com|加速域名。|
|StartTime|String|2015-12-03|查询指定日期。|
|AllUrlList| | |全部热门URLlist。|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/a0.m3u8](http://test.com/nn_live/nn_x64/a0.m3u8)|完整的Url地址。|
|  └VisitData|String|161673|访问次数。|
|  └VisitProportion|Float|0.35|访问占比。|
|  └Flow|String|460486880| 流量。

 单位：byte

 |
|  └FlowProportion|Float|0.35|流量占比。|
|Url200List| | |返回为2xx的Urllist。|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8)|完整的Url地址。|
|  └VisitData|String|161673|访问次数。|
|  └VisitProportion|Float|0.35|访问占比。|
|  └Flow|String|460486880| 流量。

 单位：byte

 |
|  └FlowProportion|Float|0.35|流量占比。|
|Url300List| | |返回为3xx的Urllist。|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/a0.m3u8](http://test.com/nn_live/nn_x64/a0.m3u8)|完整的Url地址。|
|  └VisitData|String|161673|次数。|
|  └VisitProportion|Float|0.35|访问占比。|
|  └Flow|String|460486880| 流量。

 单位：byte

 |
|  └FlowProportion|Float|0.35|流量占比。|
|Url400List| | |返回为4xx的Urllist。|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8)|完整的Url地址。|
|  └VisitData|String|1884|次数。|
|  └VisitProportion|Float|0.35|访问占比。|
|  └Flow|String|460486880| 流量。

 单位：byte

 |
|  └FlowProportion|Float|0.35|流量占比。|
|Url500List| | |返回为5xx的Urllist。|
|  └UrlDetail|String|[http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8](http://test.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8)|完整的Url地址。|
|  └VisitData|String|161673|次数。|
|  └VisitProportion|Float|0.35|访问占比。|
|  └Flow|String|460486880| 流量。

 单位：byte

 |
|  └FlowProportion|Float|0.35|流量占比。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit&DomainName=test.com
&StartTime=2015-12-03
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "AllUrlList":{
            "UrlList":[
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/a0.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                },
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"37",
                    "VisitProportion":0.35
                }
            ]
        },
        "DomainName":"test.com",
        "RequestId":"64D28B53-5902-409B-94F6-FD46680144FE",
        "StartTime":"2015-12-03",
        "Url200List":{
            "UrlList":[
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                },
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUDMlPTIwMTxMDk5ZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"3",
                    "VisitProportion":0.35
                }
            ]
        },
        "Url300List":{
            "TopUrlVisitModel":[]
        },
        "Url400List":{
            "UrlList":[
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"1884",
                    "VisitProportion":0.35
                },
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SEEwODgmpbmRleZPTE,/HNJSMPP360.ts",
                    "VisitData":"1",
                    "VisitProportion":0.35
                }
            ]
        },
        "Url500List":{
            "UrlList":[
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                    "VisitData":"161673",
                    "VisitProportion":0.35
                },
                {
                    "Flow":"460486880",
                    "FlowProportion":0.35,
                    "UrlDetail":"http://test.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                    "VisitData":"3",
                    "VisitProportion":0.35
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


