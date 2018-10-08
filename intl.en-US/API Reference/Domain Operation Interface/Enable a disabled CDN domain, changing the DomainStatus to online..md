# StartCdnDomain {#reference_gwk_pry_5db .reference}

Enables an accelerated domain name with a status of "disabled" and changes the DomainStatus to online.

**Note:** If the account corresponding to the domain name is in arrears or the domain name is illegal, you cannot call this interface to enable the CDN domain name in the normal way.

## Request Parameters {#section_j31_wry_5db .section}

|Parameters|Type|Required|Example values|Description|
|----------|----|--------|--------------|-----------|
|Action|String|Yes|StartCdnDomain| The name of this interface. Value:

 StartCdnDomain

 |
|DomainName|String|Yes|www.yourdomain.com|The name of this interface. |

## Return Parameters {#section_t25_csy_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| Request ID

 |

## Example {#section_mkz_gsy_5db .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=test.com&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


