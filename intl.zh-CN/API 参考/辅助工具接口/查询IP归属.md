# 查询IP归属 {#reference_pwp_rkl_vdb .reference}

验证指定的IP是否为阿里云CDN节点的IP地址。

## 请求参数 {#section_awt_vkl_vdb .section}

|参数|类型|必要|描述|
|:-|:-|:-|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeIpInfo|
|IP|String|是|指定IP地址，不支持批量|

## 返回参数 {#section_kcx_3ml_vdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID|
|CdnIp|String|是否属于阿里云CDN节点，True，属于；False，不属于|
|ISP|String|所属运营商|
|Region|String|所属地区|

## 特殊错误码 {#section_fpk_kml_vdb .section}

|错误代码|描述|Http 状态码|语义|
|:---|:-|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止|
|MissingParameter|The specified value of parameter IP is not valid.|400|缺少IP参数|
|InvalidIP.ValueNotSupported|The specified value of parameter IP is not supported.|400|IP格式不正确|

## 示例 {#section_nwt_vkl_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeIpInfo&IP=1.2.3.4
&公共请求参数
```

**返回示例**

-   JSON格式

    ```
    {
        "Region": "中国-贵州省-贵阳市",
        "RequestId": "123847FA-9A00-4426-83B8-B4B45D475930",
        "ISP": "电信",
        "CdnIp": "True"
    }
    ```


-   XML格式

    ```
    
      中国-贵州省-贵阳市
      AA880DA3-570B-4407-AC5D-D28E0D28A290
      电信
      True
    
    ```


