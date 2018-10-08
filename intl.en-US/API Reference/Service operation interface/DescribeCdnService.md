# DescribeCdnService {#reference_tnf_qtt_vdb .reference}

Queries the CDN service status,  including current billing method, service subscription time, start of next billing method and current service status.

## Request parameters {#section_v4v_5tt_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeCdnService|The name of this interface. Value: DescribeCdnService|

## Return Parameters {#section_ukj_xtt_vdb .section}

|Parameters|Type|Example values|Description|
|InternetChargeType|String|PayByTraffic| Billing method:

 -   PayByTraffic
-   PayByBandwidth

 |
|OpeningTime|String|2014-02-28T13:11:49Z|Service subscription time, ISO 8601 time format.|
|ChangingChargeType|String|PayByTraffic| Start of next billing method.

 -   Paybytraffic
-   PayByBandwidth

 |
|ChangingAffectTime|String|2014-11-27T16:00:00Z|GMT.|
|OperationLocks| | |Operation locking status, such as arrearage and security.|
|  └LockReason|String|financial|The reason of operation locking.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|
|InstanceId|String|aliuid|The instance ID.|

## Examples {#section_sz4_ctt_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=DescribeCdnService&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "ChangingAffectTime":"2014-11-27T16:00:00Z",
        "ChangingChargeType":"PayByBandwidth",
        "InternetChargeType":"PayByTraffic",
        "OpeningTime":"2014-02-28T13:11:49Z",
        "OperationLocks":{
            "LockReason":[]
        
        "RequestId":"BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


