# DescribeDomainBpsDataByTimeStamp {#reference3217 .reference}

获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位：bit/second。

**说明：** 

-   不支持批量域名查询。
-   时间精确到5分钟粒度。

## 请求参数 { .section}

|参数|类型|必要|描述|
|--|--|--|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainBpsDataByTimeStamp|
|DomainName|String|是|要查询的域名，不能为空。|
|LocationNames|String|是| -   需要查询目标区域列表，用“,”隔开，不能为空。
-   Location名通过DescribeCdnRegionAndIsp接口获得。

 |
|IspNames|String|是| -   需要查询目标Isp列表，用“,”隔开，不能为空。
-   ISP名通过DescribeCdnRegionAndIsp接口获得。

 |
|TimePoint|String|是|查询目标时间点。-   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息|
|TimePoint|String|时间点|
|BpsDataList|BpsDataModel\[\]|每个Locate、ISP对应的bps值|

## BpsDataModel { .section}

|名称|类型|描述|
|--|--|--|
|LocationName|String|节点名|
|IspName|String|Isp名|
|Bps|Long|对应的带宽值|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByTimeStamp&DomainName=example.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&TimePoint=2016-08-01T22:00:00Z
&<公共请求参数>
```

返回示例：

JSON格式

```language-json
{
    "TimeStamp": "2016-08-01T22:00:00Z", 
    "BpsDataList": {
        "BpsDataModel": [
            {
                "LocationName": "Liaoning", 
                "Bps": 880996111, 
                "IspName": "telecom"
            }, 
            {
                "LocationName": "Liaoning", 
                "Bps": 52119553, 
                "IspName": "unicom"
            }, 
            {
                "LocationName": "Guangxi", 
                "Bps": 51295137, 
                "IspName": "telecom"
            }, 
            {
                "LocationName": "Guangxi", 
                "Bps": 18673571, 
                "IspName": "unicom"
            }
        ]
    }, 
    "RequestId": "7682DE14-3B4D-48D0-9B7C-DD3C8C3E1C78", 
    "DomainName": "example.cn"
}

```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名, 无法操作|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidTimePoint.Malformed|Specified TimePoint malformed.|400|TimePoint格式错误|
|InvaildParameter|IspNames Not Supported|400|ISP不支持|
|InvaildParameter|LocationNames Not Supported|400|Location不支持|

