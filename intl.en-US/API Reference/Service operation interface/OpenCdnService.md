# OpenCdnService {#reference_llj_4bt_vdb .reference}

Subscribe to the CDN service. Only after subscribing can you perform domain name operations.

-   A single user can only subscribe once. 
-   Subscription restrictions: The account must have passed real-name registration.

**Note:** Make sure that before using this interface, you fully know billing method and price of CDN.  For more information, see [Price overview](../intl.en-US/Pricing/Price overview.md#).

## Request parameters {#section_lgd_3rt_vdb .section}

|Name|Type|Required|Instance Value|Description|
|Action|String|Yes|OpenCdnService|The name of this interface.  Value: OpenCdnService|
|InternetChargeType|String|Yes|PayByTraffic|Billing type of provisioning service:

 -   PayByTraffic
-   PayByBandwidth

 If the user does not make a choice, the default charging type is PayByTraffic.|

## Return parameters {#section_zgb_cst_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_sz4_ctt_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=OpenCdnService&InternetChargeType=PayByBandwidth&Public request parameter
```

**Example of normal return**

-   JSON format

    ```
    
        "RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message:" The request processing has failed due to some unknown error .",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


