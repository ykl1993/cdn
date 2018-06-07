# AddCdnDomain {#reference_zyj_bw1_5db .reference}

Add CDN domain names. At one time, you can only submit one domain name. A single user can add up to 20 domain names.

Restrictions:

-   Before creating a CDN domain name, the CDN service must be activated.
-   The CDN domain name must complete registration process. 
-   If the origin site content is not on the Alibaba Cloud platform, it must be reviewed. The review will be completed before the next workday.

## Request parameters {#section_cch_pjg_mdb .section}

|Parameters|Parameters|Required|Example values|Description|
|:---------|:---------|:-------|:-------------|:----------|
|Action|String|Yes|AddCdnDomain| The name of this interface.  Value: 

 AddCdnDomain

 |
|CdnType|String|Yes|web| The CDN domain business type.  Value range:

-   web: distribution of images and small files. 
-   download: acceleration of large file downloads.
-   video: acceleration of video and audio on demand.
-   liveStream：acceleration of live streaming media.

 |
|DomainName|String|Yes|www.yourdomain.com| The domain name that requests access to CDN.  Supports generic domain name,  and starts with “.”, such as .a.com.

 |
|Checkurl|String|No|www.yourdomain.com/test.html| Health check of the source site.

 |
|LiveType|String|No|liveEdge| Live edge streaming.

 |
|OwnerAccount|String|No|your OwnerAccount| OwnerAccount。

 |
|Priorities|String|No|20| Priorities, separated by comma, and the number is consistent with sources.

 |
|Region|String|No|cn-shanghai| Unit information of live domain name.

 |
|ResourceGroupId|String|No|your resourceGroupId| ID of the resource group.

 |
|Scope|String|No|domestic| Value range:

-   domestic
-   overseas
-   global

Default value: domestic.  The setting is effective for international users, domestic users of level3 or above.

 |
|SourcePort|String|No|80| 443 and 80 can be specified. Default value: 80

 443 port performs https source.  OSS does not suppport 443 port.

 |
|SourceType|String|No|domain| Source type.  Value range:

-   ipaddr：IP source site.
-   domain：source site of domain name. 
-   oss：oss is the source site.

**Note:** If you select the business type of live streaming media acceleration, the source site type and information is not required.

 |
|Sources|String|No|www.yourdomain.com| Source address, can be IP or domain name.

 -   IP supports up to 20, which are seperated by comma.
-   Only one domain name can be entered, and IP and domain name cannot be entered at the same time.
-   If the business type is live streaming media acceleration, the source address is not required to enter. If the business type is other type, source address is required \(inner user, the type is common source, and type enum value can be entered\).

 |
|TopLevelDomain|String|No|www.yourTopLevelDomain| Top-level scheduling domain.

 |

## Return Parameters {#section_hdn_f2c_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| RequestId

 |

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
1. http://cdn.aliyuncs.com?Action=AddCdnDomain&CdnType=web&SourceType=domain&DomainName=test.com&Sources=test.com&<Public request parameter>
```

**Normal return example**

-   JSON format

    ```
     
         "RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
    
    ```


**Exception return example**

-   JSON format

    ```
     
        "Code":"InternalError", 
         "Hostid": "maid ", 
         "Message":"The request processing has failed due to some unknown error.",
         "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


