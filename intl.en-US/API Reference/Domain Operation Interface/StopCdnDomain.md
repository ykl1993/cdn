# StopCdnDomain {#reference_vdv_zrx_5db .reference}

Deactivate a CDN domain, changing the "DomainStatus" to "offline".

**Note:** 

-   After a CDN domain is deactivated, its information is still retained and the system will automatically perform back-to-source processing for requests to the CDN domain.
-   We recommend that you use the StopCdnDomain interface to suspend acceleration for the domain name if, for the moment, you do not require acceleration for a certain domain name.

## Request parameters {#section_zv2_w1y_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|StopCdnDomain| The name of this interface. Value: 

 StopCdnDomain

 |
|DomainName|String|Yes|www.yourdomain.com| The domain name, which requests access to the CDN.

 |

## Return Parameters {#section_tlm_hby_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| Request ID

 |

## Examples {#section_ur3_qby_5db .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=StopDomain&DomainName=test.com&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"324AEFFF-308C-4DA7-8CD3-01B277B98F28"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message:" The request processing has failed due to some unknown error .",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


