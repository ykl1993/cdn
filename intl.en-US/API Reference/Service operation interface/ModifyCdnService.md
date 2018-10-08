# ModifyCdnService {#reference_kdm_l5t_vdb .reference}

Modifies the CDN service billing methods.

-   You must first subscribe to the service to perform this operation.
-   Changes of the billing methods take effect at 00:00 the next day. If multiple changes are performed, the latest change prevails. 
-   Billing methods: 
    -   PayByBandwidth.
    -   PayByTraffic.

## Request parameters {#section_mbs_s5t_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|ModifyCdnService|The name of this interface. Value: ModifyCdnService|
|InternetChargeType|String|Yes|PayByTraffic|Service subscription billing method.

 -   PayByTraffic
-   PayByBandwidth

 Users must specify a method between PayByTraffic and PayByBandwidth.|

## Return Parameters {#section_gl2_3xt_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_sz4_ctt_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=ModifyCdnService&InternetChargeType=PayByTraffic&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


