# DeleteCdnDomain {#reference_tw3_cly_5db .reference}

Delete an added CDN domain name.

**Note:** 

-   Be careful when performing this operation \(we recommend that you restore the domain name A record at the DNS provider before deleting the domain name\) to ensure the domain name can still be accessed after deletion.
-   After DeleteCdnDomain is called successfully, all the records associated with the CDN domain name will be deleted. If you only wish to suspend use of the CDN domain name temporarily, we recommend that you use the StopCdnDomain interface.

## Request parameters {#section_f3c_4ly_5db .section}

|Name|Type|Required|Example values|Description|
|:---|:---|:-------|:-------------|:----------|
|Action|String|Yes|DeleteCdnDomain|The name of this interface. Value:

DeleteCdnDomain|
|DomainName|String|Yes|www.yourdomain.com| The CDN domain name to be deleted.

 |
|ResourceGroupId|String|No|your resourceGroupId| The resource group ID.

 |

## Return Parameters {#section_pqc_xly_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_tgd_fmy_5db .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=DeleteDomain&DomainName=test.com&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"94E3559F-7B6A-4A5E-AFFD-44E2A208A249"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


