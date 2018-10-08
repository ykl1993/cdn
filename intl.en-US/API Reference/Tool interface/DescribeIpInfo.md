# DescribeIpInfo {#reference_pwp_rkl_vdb .reference}

Verifies whether the specified IP address is the IP address of an Alibaba Cloud CDN node.

## Request parameters {#section_awt_vkl_vdb .section}

|Parameter|Type| Required|Description|
|:--------|:---|:--------|:----------|
|Action|String|Yes|Operation interface name, which is a required parameter. Value: DescribeIpInfo|
|IP|String|Yes.|Specified IP address. Batch IP addresses are not supported.|

## Return parameters {#section_kcx_3ml_vdb .section}

|Parameters|Type|Description|
|:---------|:---|:----------|
|RequestId|String|Request ID|
|CdnIp|String|Whether the specified IP address belongs to an Alibaba Cloud CDN node; optional values: True \(Yes\) and False \(No\)|
|ISP|String|Carrier|
|Region|String|Region|

## Special error code {#section_fpk_kml_vdb .section}

|Error code|Description|HTTP Status Codes|Meaning|
|:---------|:----------|:----------------|:------|
|Throttling|Request was denied due to request throwing.|503|Request restricted by traffic control|
|OperationDenied|Your account does not open CDN service yet.|403| CDN service not activated|
|OperationDenied|Your CDN service is suspended.|403|CDN service stopped|
|MissingParameter|The specified value of parameter IP is not valid.|400| IP address parameter missing|
|InvalidIP.ValueNotSupported|The specified value of parameter IP is not supported.|400| Incorrect IP address format|

## Examples {#section_nwt_vkl_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeIpInfo&IP=1.2.3.4
&Public request parameter
```

**Return example**

-   JSON format

    ```
    
        "Region": "China-Guizhou province-Guiyang city",
        "RequestId": "123847FA-9A00-4426-83B8-B4B45D475930",
        "ISP": "Telecom",
        "CdnIp": "True"
    
    ```


-   XMLformat

    ```
    
      China-Guizhou province-Guiyang city
      AA880DA3-570B-4407-AC5D-D28E0D28A290
      Telecom
      True
    
    ```


