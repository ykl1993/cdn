# DescribeDomainRegionData {#reference_dmq_5ym_vdb .reference}

Obtain the regional user distribution of CDN domains with day granularity.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_qtb_bzm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainRegionData|The name of this interface.  Value: DescribeDomainRegionData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, the system queries all domain names.|
|EndTime|String|No|2016-03-13| -   The end time must be later than the start time, and adopts Beijing time.
-   Format: YYYY-MM-DD.

 |
|StartTime|String|No|2016-03-13| Start time of data query, and Beijing time is adopted.

 -   Format is: YYYY-MM-DD.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_wb1_hzm_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|2E5AD83F-BD7B-462E-8319-2E30E305519A|The ID of the request.|
|DomainName|String|test.test.com|CDN domain name.|
|DataInterval|String|86400|Time interval.|
|StartTime|String|2016-03-13|Start time of data query.|
|EndTime|String|2016-03-13|End time of data query.|
|Value| | |value.|
|  └Region|String|Japan|Region information.|
|  └Proportion|String|0.01155980271270037|Access proportion data. If the return value is 90, the access proportion is 90%.|
|  └RegionEname|String|japan|Region name in English.|
|  └AvgObjectSize|String|800019.0| Average response size. 

 Unit: byte.

 |
|  └AvgResponseTime|String|5183.666666666667| Average response time.

 Unit: milliseconds.

 |
|  └Bps|String|380.9614285714286|Bandwidth.|
|  └ByteHitRate|String|100.0|Bytes hit rate. If the return value is 90, the bytes hit rate is 90%.|
|  └Qps|String|5.9523809523809524E-5|Per-second query rate.|
|  └ReqErrRate|String|0.0|Request error rate. If the return value is 90, the request error rate is 90%.|
|  └ Reqhitrate|String|100.0|Request hit rate. If the return value is 0.5, the request hit rate is 0.5%.|
|  └AvgResponseRate|String|154.3345765545624| Average download speed.

 Unit: byte/second.

 |
|  └TotalBytes|String|2400057|Total traffic.|
|  └BytesProportion|String|0.003544181046236794|Total traffic proportion data. If the return value is 90, the traffic proportion is 90%.|
|  └TotalQuery|String|3|Total number of requests.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainRegionData&DomainName=test.com
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
        "RequestId":"2E5AD83F-BD7B-462E-8319-2E30E305519A",
        "StartTime":"2016-03-13",
        "Value":{
            "RegionProportionData":[
                
                    "AvgObjectSize":"800019.0",
                    "AvgResponseRate":"154.3345765545624",
                    "AvgResponseTime":"5183.666666666667",
                    "Bps":"380.9614285714286",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.003544181046236794",
                    "Proportion":"0.01155980271270037",
                    "Qps":"5.9523809523809524E-5",
                    "Region":"Japan",
                    "RegionEname":"",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2400057",
                    "TotalQuery":"3"
                
                
                    "AvgObjectSize":"1953033.5543209878",
                    "AvgResponseRate":"1397.1430909315718",
                    "AvgResponseTime":"1397.8765432098764",
                    "Bps":"25110.431412698414",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.23360872886644055",
                    "Proportion":"0.31211467324291",
                    "Qps":"0.0016071428571428571",
                    "Region":"Tibet Autonomous Region",
                    "RegionEname":"xizang",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"158195717",
                    "TotalQuery":"81"
                
                
                    "AvgObjectSize":"2888253.7875",
                    "AvgResponseRate":"787.8073097249128",
                    "AvgResponseTime":"3666.193181818182",
                    "Bps":"40343.86242857143",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.37532921137846464",
                    "Proportion":"0.33908754623921084",
                    "Qps":"0.001746031746031746",
                    "Region":"The city of Chongqing",
                    "RegionEname":"zhongqing",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"254166333",
                    "TotalQuery":"88"
                
                
                    "AvgObjectSize":"2522291.608247423",
                    "AvgResponseRate":"1711.4277340197823",
                    "AvgResponseTime":"1473.7938144329896",
                    "Bps":"38835.2834920635",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"0.3612945179094354",
                    "Proportion":"0.37376695437731194",
                    "Qps":"0.0019246031746031746",
                    "Region":"The city of Tianjin",
                    "RegionEname":"tianjin",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"244662286",
                    "TotalQuery":"97"
                
                
                    "AvgObjectSize":"2855944.0483660134",
                    "AvgResponseRate":"1210.9708048576356",
                    "AvgResponseTime":"2358.392156862745",
                    "Bps":"69358.64117460318",
                    "ByteHitRate":"99.99291705425965",
                    "BytesProportion":"0.6452610763393265",
                    "Proportion":"0.5895499383477188",
                    "Qps":"0.0030357142857142857",
                    "Region":"Qinghai province",
                    "RegionEname":"qinghai",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.34640522875817",
                    "TotalBytes":"436959439",
                    "TotalQuery":"153"
                
                
                    "AvgObjectSize":"2483988.2375000003",
                    "AvgResponseRate":"324.9427676080411",
                    "AvgResponseTime":"7644.386904761905",
                    "Bps":"66239.68633333335",
                    "ByteHitRate":"99.99999999999999",
                    "BytesProportion":"0.6162446463192347",
                    "Proportion":"0.6473489519112207",
                    "Qps":"0.0033333333333333335",
                    "Region":"Hainan province",
                    "RegionEname":"Hainan",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"417310023",
                    "TotalQuery":"168"
                
                
                    "Maid": "1945529.152238806 ",
                    "AvgResponseRate":"1319.43005273653",
                    "AvgResponseTime":"1474.5223880597016",
                    "Bps":"62071.644380952384",
                    "ByteHitRate":"99.99983347455928",
                    "BytesProportion":"0.5774682921278322",
                    "Proportion":"0.7745067817509248",
                    "Qps":"0.0039880952380952385",
                    "Region":"The city of Shanghai",
                    "RegionEname":"shanghai",
                    "Reqerrrate": 0.0 ",
                    "ReqHitRate":"99.50248756218906",
                    "TotalBytes":"391051359",
                    "TotalQuery":"201"
                
                
                    "AvgObjectSize":"2273425.479253112",
                    "AvgResponseRate":"1223.3552235839977",
                    "AvgResponseTime":"1858.3526970954356",
                    "Bps":"86967.5461111111",
                    "ByteHitRate":"98.60251863101267",
                    "BytesProportion":"0.8090811968039774",
                    "Proportion":"0.9286374845869297",
                    "Qps":"0.004781746031746032",
                    "Region":"The city of Beijing",
                    "RegionEname":"beijing",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"96.2655601659751",
                    "TotalBytes":"547895540",
                    "TotalQuery":"241"
                
                
                    "AvgObjectSize":"2813953.1475538164",
                    "AvgResponseRate":"512.8134924297486",
                    "AvgResponseTime":"5487.283757338552",
                    "Bps":"228242.86641269844",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"2.1234014270475434",
                    "Proportion":"1.9690197287299631",
                    "Qps":"0.010138888888888888",
                    "Region":"Ningxia Hui Autonomous Region",
                    "RegionEname":"ningxia",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"1437930058",
                    "TotalQuery":"511"
                
                
                    "AvgObjectSize":"2366583.779623288",
                    "AvgResponseRate":"1152.4327405034373",
                    "AvgResponseTime":"2053.554794520548",
                    "Bps":"219378.5598888889",
                    "ByteHitRate":"100.00000000000001",
                    "BytesProportion":"2.040934529315853",
                    "Proportion":"2.250308261405672",
                    "Qps":"0.011587301587301587",
                    "Region":"Gilin province",
                    "RegionEname":"Jilin",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"1382084927",
                    "TotalQuery":"584"
                
                
                    "AvgObjectSize":"1897704.4197019867",
                    "AvgResponseRate":"476.60455862620415",
                    "AvgResponseTime":"3981.7168874172185",
                    "Bps":"181938.64595238096",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"1.6926214892159708",
                    "Proportion":"2.3273736128236746",
                    "Qps":"0.011984126984126984",
                    "Region":"Gansu province",
                    "RegionEname":"Gansu",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"1146213469",
                    "TotalQuery":"604"
                
                
                    "AvgObjectSize":"2623223.5489683636",
                    "AvgResponseRate":"786.5196031941114",
                    "AvgResponseTime":"3335.2297111416783",
                    "Bps":"302711.6698571429",
                    "ByteHitRate":"99.99996931440107",
                    "BytesProportion":"2.816203642467227",
                    "Proportion":"2.8013255240443895",
                    "Qps":"0.014424603174603175",
                    "Region":"Xinjiang Uygur Autonomous Region",
                    "RegionEname":"xinjiang",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.8624484181568",
                    "TotalBytes":"1907083520",
                    "TotalQuery":"727"
                
                
                    "AvgObjectSize":"2816389.5711772665",
                    "AvgResponseRate":"537.274830290738",
                    "AvgResponseTime":"5241.9905277401895",
                    "Bps":"330366.9671587302",
                    "ByteHitRate":"99.99996955766207",
                    "BytesProportion":"3.0734879058423363",
                    "Proportion":"2.847564734895191",
                    "Qps":"0.014662698412698412",
                    "Region":"Inner Mongolia Autonomous Region",
                    "RegionEname":"neimenggu",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.86468200270636",
                    "TotalBytes":"2081311893",
                    "TotalQuery":"739"
                
                
                    "AvgObjectSize":"2519812.7500674766",
                    "AvgResponseRate":"784.3618585093111",
                    "AvgResponseTime":"3212.5641025641025",
                    "Bps":"296377.9758412699",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"2.7572796764166547",
                    "Proportion":"2.8552712700369915",
                    "Qps":"0.014702380952380953",
                    "Region":"Guizhou province",
                    "RegionEname":"Guizhou",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"1867181247",
                    "TotalQuery":"741"
                
                
                    "AvgObjectSize":"2841349.462781955",
                    "AvgResponseRate":"936.6710791561273",
                    "AvgResponseTime":"3033.4548872180453",
                    "Bps":"359904.2652857143",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"3.348280901477785",
                    "Proportion":"3.0749075215782984",
                    "Qps":"0.015833333333333335",
                    "Region":"Shaanxi province",
                    "RegionEname":"shanxixian",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2267396871",
                    "TotalQuery":"798"
                
                
                    "AvgObjectSize":"2751993.832670808",
                    "AvgResponseRate":"1809.5402913913995",
                    "AvgResponseTime":"1520.824844720497",
                    BPS: 351643.65639682545 ",
                    "ByteHitRate":"99.8809108401154",
                    "BytesProportion":"3.2714303563604967",
                    "Proportion": 3.101880394574599 ",
                    "Qps":"0.01597222222222222",
                    "Region":"Jiangxi province",
                    "RegionEname":"Jiangxi",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"98.88198757763975",
                    "TotalBytes":"2215355035",
                    "TotalQuery":"805"
                
                
                    "AvgObjectSize":"2473513.185",
                    "AvgResponseRate":"1154.391434785841",
                    "AvgResponseTime":"2142.6988372093024",
                    "Bps":"337654.18080952385",
                    "ByteHitRate":"99.99985277977696",
                    "BytesProportion":"3.141282707530976",
                    "Proportion":"3.313810110974106",
                    "Qps":"0.017063492063492062",
                    "Region":"Fujian province",
                    "RegionEname":"Fujian",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.4186046511628",
                    "TotalBytes":"2127221339",
                    "TotalQuery":"860"
                
                
                    "AvgObjectSize":"2529717.982589286",
                    "AvgResponseRate":"1235.7418245535987",
                    "AvgResponseTime":"2047.125",
                    "Bps":"359782.1130793651",
                    "ByteHitRate":"99.88374126237764",
                    "BytesProportion":"3.3471444884395347",
                    "Proportion":"3.4525277435265105",
                    "Qps":"0.017777777777777778",
                    "Region":"Shanxi province",
                    "RegionEname":"shanxi",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.55357142857143",
                    "TotalBytes":"2266627312",
                    "TotalQuery":"896"
                
                
                    "AvgObjectSize":"2768882.4563117456",
                    "AvgResponseRate":"1662.686634908582",
                    "AvgResponseTime":"1665.3062568605928",
                    "Bps":"400389.1932857143",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"3.7249224817393896",
                    "Proportion":"3.5103267570900125",
                    "Qps":"0.018075396825396824",
                    "Region":"Yunnan province",
                    "RegionEname":"yunnan",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2522451917",
                    "TotalQuery":"911"
                
                
                    "AvgObjectSize":"2602777.413138686",
                    "AvgResponseRate":"1028.303387588414",
                    "AvgResponseTime":"2531.1376433785194",
                    "Bps":"396200.5617777778",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"3.685954577676852",
                    "Proportion":"3.695283600493218",
                    "Qps":"0.01902777777777778",
                    "Region":"Hebei province",
                    "RegionEname":"Hebei",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"2496063539",
                    "TotalQuery":"959"
                
                
                    "AvgObjectSize":"2828102.81425943",
                    "AvgResponseRate":"884.3783424312907",
                    "AvgResponseTime":"3197.8426862925485",
                    "Bps":"487959.9617619048",
                    "ByteHitRate":"99.99993802509998",
                    "BytesProportion":"4.5396156096015785",
                    "Proportion":"4.188501849568434",
                    "Qps":"0.02156746031746032",
                    "Region":"Hubei province",
                    "RegionEname":"Hubei",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.72401103955842",
                    "TotalBytes":"3074147759",
                    "TotalQuery":"1087"
                
                
                    "AvgObjectSize":"2553441.9855605382",
                    "AvgResponseRate":"1127.3220113227628",
                    "AvgResponseTime":"2265.0511210762334",
                    "Bps":"451918.7006190476",
                    "ByteHitRate":"99.91296907710742",
                    "BytesProportion":"4.2043145921101575",
                    "Proportion":"4.296393341553637",
                    "Qps":"0.022123015873015874",
                    "Region":"Zhejian province",
                    "RegionEname":"zhejiang",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.64125560538116",
                    "TotalBytes":"2847087813",
                    "TotalQuery":"1115"
                
                
                    "AvgObjectSize":"2825230.7105726874",
                    "AvgResponseRate":"1330.4354698914951",
                    "AvgResponseTime":"2123.5383259911896",
                    BPS: 508989.9772222223 ",
                    "ByteHitRate":"99.7790833225895",
                    "BytesProportion":"4.73526319123739",
                    "Proportion":"4.37345869297164",
                    "Qps":"0.02251984126984127",
                    "Region":"Jiangsu province",
                    "RegionEname":"Jiangsu",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.64757709251101",
                    "TotalBytes":"3206636856",
                    "TotalQuery":"1135"
                
                
                    "AvgObjectSize":"2707689.0548415496",
                    "AvgResponseRate":"1339.8235569585188",
                    "AvgResponseTime":"2020.9295774647887",
                    "Bps":"488243.6136984127",
                    "ByteHitRate":"99.99857147165532",
                    "BytesProportion":"4.54225449569792",
                    "Proportion":"4.37731196054254",
                    QPS: 0.02253968253968254 ",
                    "Region":"Hunan province",
                    "RegionEname":"Hunan",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.03169014084507",
                    "TotalBytes":"3075934766",
                    "TotalQuery":"1136"
                
                
                    "AvgObjectSize":"2763049.585677308",
                    "AvgResponseRate":"1397.6178986771317",
                    "AvgResponseTime":"1976.9706643658326",
                    "Bps":"508313.40790476196",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"4.728968894829482",
                    "Proportion":"4.465937114673243",
                    "Qps":"0.022996031746031747",
                    "Region":"Heilongjiang province",
                    "RegionEname":"Heilongjiang",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"3202374469",
                    "Totalquery": "1159"
                
                
                    "AvgObjectSize":"2635213.5717817564",
                    "AvgResponseRate":"1452.8561771775414",
                    "AvgResponseTime":"1813.8158567774935",
                    "Bps":"490651.66979365086",
                    "ByteHitRate":"99.99999999999999",
                    "BytesProportion":"4.564657253906334",
                    "Proportion":"4.519882860665844",
                    "Qps":"0.023273809523809523",
                    "Region":"Liaoning province",
                    "RegionEname":"Liaoning",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"3091105519",
                    "TotalQuery":"1173"
                
                
                    "AvgObjectSize":"2651141.2248081844",
                    "AvgResponseRate":"1502.2255494727121",
                    "AvgResponseTime":"1764.8090366581416",
                    "Bps":"493617.2470952381",
                    "ByteHitRate":"99.962662755313",
                    "BytesProportion":"4.592246773671759",
                    "Proportion":"4.519882860665844",
                    "Qps":"0.023273809523809523",
                    "Region":"Anhui province",
                    "RegionEname":"anhui",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.65899403239557",
                    "TotalBytes":"3109788656",
                    "TotalQuery":"1173"
                
                
                    "AvgObjectSize":"2765505.7641129037",
                    "AvgResponseRate":"469.5304824766785",
                    "AvgResponseTime":"5889.938709677419",
                    "Bps":"544321.7694444446",
                    "ByteHitRate":"99.3034652219695",
                    "BytesProportion":"5.063963838946395",
                    "Proportion":"4.778051787916153",
                    "Qps":"0.024603174603174603",
                    "Region":"Guangxi Zhuang Autonomous Region",
                    "RegionEname":"Guangxi",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"98.79032258064517",
                    "TotalBytes":"3429227147",
                    "Totalquery": "1240"
                
                
                    "AvgObjectSize":"2197253.41769852",
                    "AvgResponseRate":"720.671411528823",
                    "AvgResponseTime":"3048.897711978466",
                    "Bps":"518272.7902698413",
                    "ByteHitRate":"99.99678589314689",
                    "BytesProportion":"4.821623561583812",
                    "Proportion":"5.725955610357583",
                    "Qps":"0.029484126984126984",
                    "Region":"Sichuan province",
                    "RegionEname":"sichuan",
                    "ReqErrRate":"0.0",
                    "Reqhitrate": 99.93270524899057 ",
                    "TotalBytes":"3265118578",
                    "TotalQuery":"1486"
                
                
                    "AvgObjectSize":"2773648.9175943704",
                    "AvgResponseRate":"2216.86197693452",
                    "AvgResponseTime":"1251.1599488163788",
                    "Bps":"688129.0886031748",
                    "ByteHitRate":"100.0",
                    "BytesProportion":"6.4018398984302864",
                    "Proportion":"6.022657213316893",
                    "Qps":"0.03101190476190476",
                    "Region":"Shandong province",
                    "RegionEname":"shandong",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"100.0",
                    "TotalBytes":"4335213258",
                    "TotalQuery":"1563"
                
                
                    "AvgObjectSize":"2566371.868045113",
                    "AvgResponseRate":"1091.8003744598548",
                    "AvgResponseTime":"2350.5870927318297",
                    "Bps":"650147.539904762",
                    "ByteHitRate":"99.99998447727191",
                    "BytesProportion":"6.048487892405889",
                    "Proportion":"6.149815043156597",
                    "Qps":"0.03166666666666667",
                    "Region":"Henan province",
                    "RegionEname":"Henan",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.93734335839599",
                    "TotalBytes":"4095929501",
                    "TotalQuery":"1596"
                
                
                    "AvgObjectSize":"2505782.0102497404",
                    "AvgResponseRate":"1040.446859646019",
                    "AvgResponseTime":"2408.3709677419356",
                    "Bps":"764462.3847142858",
                    "ByteHitRate":"99.82548062184921",
                    "BytesProportion":"7.111987963257421",
                    "Proportion":"7.405980271270037",
                    "Qps":"0.03813492063492063",
                    "Region":"Guangdong province",
                    "RegionEname":"Guangdong",
                    "ReqErrRate":"0.0",
                    "ReqHitRate":"99.37565036420395",
                    "TotalBytes":"4816113023",
                    "TotalQuery":"1922"
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


