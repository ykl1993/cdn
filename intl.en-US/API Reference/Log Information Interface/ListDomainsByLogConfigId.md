# ListDomainsByLogConfigId {#reference_ffg_skf_vdb .reference}

Query the list of all the domain names using a custom log configuration.

## Request parameters {#section_w3c_qmf_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|ListDomainsByLogConfigId|The name of this interface. Value: ListDomainsByLogConfigId|
|Configid|String|Yes|123|Custom configuration ID.|
|Version|String|No|2014-11-11|API version.|

## Return Parameters {#section_wpp_xmf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request.|
|Domains|String|\[ “abc.com”, “a.b.c.com” \]|Domain name list.|

## Examples {#section_gmk_1nf_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=ListDomainsByLogConfigId&ConfigId=9732E117-8A37-49FD-A36F-ABBB87556CA7&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Domains":{
            "Domain":[
                "abc.com",
                "a.b.c.com"
            
        
        "RequestId":"9732E117-8A37-49FD-A36F-ABBB87556CA7"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Domains":{
            "Domain":[
                "abc.com",
                "a.b.c.com"
            
        
        "RequestId":"9732E117-8A37-49FD-A36F-ABBB87556CA7"
    
    ```


