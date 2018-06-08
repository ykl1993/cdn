# ModifyDomainCustomLogConfig {#reference_w1y_nnf_vdb .reference}

Modify custom log configurations under a domain name.

## Request parameters {#section_u2t_4nf_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|ModifyDomainCustomLogConfig|The name of this interface.  Value: ModifyDomainCustomLogConfig|
|ConfigId|String|Yes|123|Log configuration ID.|
|DomainName|String|Yes|a.com|Domain name.|
|Version|String|No|2014-11-11|API version.|

## Return Parameters {#section_pg1_5nf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=ModifyDomainCustomLogConfig&DomainName=xxx&ConfigId=xxx&Public request parameter
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


