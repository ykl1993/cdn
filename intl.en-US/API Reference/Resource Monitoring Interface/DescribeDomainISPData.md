# DescribeDomainISPData {#reference_lhj_pzm_vdb .reference}

Obtain the distribution of users and carriers of CDN domain names with day granularity.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_s4r_tzm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainISPData|The name of this interface. Value: DescribeDomainISPData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, all domain names belonging to the current user are queried.|
|EndTime|String|No|2015-12-05| -   The end time must be later than the start time, and adopts Beijing time.
-   Format: YYYY-MM-DD.

 |
|StartTime|String|No|2015-12-05| -   Start time of data query, and adopts Beijing time.
-   Format: YYYY-MM-DD.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_x1z_zzm_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|DE81639B-DAC1-4C76-AB72-F34B836837D5|The ID of the request.|
|DomainName|String|test.test.com|The CDN domain name.|
|DataInterval|String|86400|Time interval.|
|StartTime|String|2016-03-14|Start time of data query.|
|EndTime|String|2016-03-14|End time of data query.|
|Value| | |List of access proportion data of each carrier.|
|  └ISP|String|Alibaba|Carrier information.|
|  └Proportion|String|0.004509176173513099|Proportion data.|
|  └IspEname|String|alibaba|Carrier name in English.|
|  └AvgObjectSize|String|7081884.7|Average response size.  Unit: bytes.|
|  └AvgResponseTime|String|79638.0|Average response time. Unit: milliseconds.|
|  └Bps|String|1311.4601296296296|Bandwidth.|
|  └ByteHitRate|String|100.0|Bytes hit rate.|
|  └Qps|String|2.3148148148148147E-5|Per-second query rate.|
|  └ReqErrRate|String|0.0|Request error rate.|
|  └ReqHitRate|String|100.0|Request hit rate.|
|  └AvgResponseRate|String|88.92594866772144|Average response speed. Unit: bytes/ms.|
|  └TotalBytes|String|7081884|Total traffic.|
|  └BytesProportion|String|0.012220518530445479|Total traffic proportion.|
|  └TotalQuery|String|1|Total number of requests.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainISPData&DomainName=test.com
&StartTime=2015-12-05
&EndTime=2015-12-07
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"86400",
        "DomainName":"downtest.cdnpe.com",
        "EndTime":"2016-03-14",
        "RequestId":"DE81639B-DAC1-4C76-AB72-F34B836837D5",
        "StartTime":"2016-03-13",
        "Value":{
            "ISPProportionData":[
                
                    "AvgObjectSize":"7081884.7",
                    "AvgResponseRate":"88.92594866772144",
                    "AvgResponseTime":"79638.0",
                    "Bps":"1311.4601296296296",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.012220518530445479",
                    "ISP":"Alibaba",
                    "IspEname":"alibaba",
                    "Proportion":"0.004509176173513099",
                    "Qps":"2.3148148148148147E-5",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"7081884",
                    "TotalQuery":"1"
                
                
                    "AvgObjectSize":"800019.0",
                    "AvgResponseRate":"154.3345765545624",
                    "AvgResponseTime":"5183.666666666667",
                    "Bps":"444.455",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.004141544558417533",
                    "ISP":"overseas ISP",
                    "IspEname":"overseas",
                    "Proportion":"0.013527528520539298",
                    "Qps":"6.944444444444444E-5",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2400057",
                    "TotalQuery":"3"
                
                
                    "AvgObjectSize":"3018642.684146342",
                    "AvgResponseRate":"1025.5028528460102",
                    "AvgResponseTime":"2943.5731707317073",
                    "Bps":"45838.64816666667",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.42713616424581613",
                    "ISP": Dr. Peng ",
                    "IspEname":"drpeng",
                    "Proportion":"0.3697524462280741",
                    "Qps":"0.0018981481481481482",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"247528700",
                    "TotalQuery":"82"
                
                
                    "AvgObjectSize":"3123166.4508771934",
                    "AvgResponseRate":"484.6396117340071",
                    "AvgResponseTime":"6444.30701754386",
                    "Bps":"65933.51396296297",
                    "ByteHitRate":"99.99999999999999",
                    "BytesProportion":"0.6143852267848392",
                    "ISP":"CERNET",
                    "IspEname":"cernet",
                    "Proportion": 0.5140460837804933 ",
                    "Qps":"0.002638888888888889",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"356040975",
                    "TotalQuery":"114"
                
                
                    "AvgObjectSize":"2116401.843961353",
                    "AvgResponseRate":"752.2096624205244",
                    "AvgResponseTime":"2813.5797101449275",
                    "Bps":"81128.73735185186",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.7559781771177001",
                    "ISP":"Tie Tong",
                    "IspEname":"tietong",
                    "Proportion":"0.9333994679172115",
                    "Qps":"0.004791666666666666",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"438095181",
                    "TotalQuery":"207"
                
                
                    "AvgObjectSize":"2723991.4195312504",
                    "AvgResponseRate":"321.5924922592767",
                    "AvgResponseTime":"8470.3203125",
                    "Bps":"129137.37100000001",
                    "ByteHitRate":"100.00000000000001",
                    "BytesProportion":"1.2033348171432345",
                    "ISP":"other",
                    "IspEname":"other",
                    "Proportion":"1.1543491004193533",
                    "Qps":"0.005925925925925926",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"697341803",
                    "TotalQuery":"256"
                
                
                    "AvgObjectSize":"1657975.598360084",
                    "AvgResponseRate":"1004.5513789924338",
                    "AvgResponseTime":"1650.463712491277",
                    "Bps":"879955.1972037038",
                    "ByteHitRate":"99.14745652563326",
                    "BytesProportion":"8.19964599032574",
                    "ISP":"Mobile",
                    "IspEname":"mobile",
                    "Proportion":"12.923298913288543",
                    "Qps":"0.06634259259259259",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"97.3831123517097",
                    "TotalBytes":"4751758064",
                    "TotalQuery":"2866"
                
                
                    "AvgObjectSize":"2640215.374074074",
                    "AvgResponseRate":"1171.525957981939",
                    "AvgResponseTime":"2253.6550352004897",
                    "Bps":"3194660.60262963",
                    "ByteHitRate":"99.99981717005271",
                    "BytesProportion":"29.768658772680293",
                    "ISP":"Unicom",
                    "IspEname":"unicom",
                    "Proportion":"29.46295711773459",
                    "Qps":"0.15125",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.96939087848179",
                    "TotalBytes":"17251167254",
                    "TotalQuery":"6534"
                
                
                    "AvgObjectSize":"2823126.71357933",
                    "AvgResponseRate":"984.184264638081",
                    "AvgResponseTime":"2868.494056463596",
                    "Bps":"6333214.260796296",
                    "ByteHitRate":"99.99968869093071",
                    "BytesProportion":"59.01449878861353",
                    "ISP":"Telecom",
                    "IspEname":"telecom",
                    "Proportion":"54.62416016593768",
                    "Qps":"0.28041666666666665",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.97523526498266",
                    "TotalBytes":"34199357008",
                    "Totalquery": "12114"
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


