# SetDomainServerCertificate {#reference_l1t_pjl_vdb .reference}

Set whether to enable the certificate function under a domain name and modify certificate information.

## Request parameters {#section_bcw_rjl_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetDomainServerCertificate|The name of this interface. Value: SetDomainServerCertificate|
|DomainName|String|Yes|www.yourdomain.com|CDN domain name of a specified certificate, which belongs to the HTTPS acceleration type.|
|ServerCertificateStatus|String|Yes|on|Whether the HTTPS certificate is enabled. Value:

-   on: enabled
-   off: disabled

 Default value: off, disabled|
|CertName|String|No|myCert1|Certificate Name.|
|PrivateKey|String|No|XXXXXXXX|Private key content. If the certificate is not enabled, the parameter is left blank. Enter the certificate content if any certificate is configured.|
|Region|String|No|cn-hangzhou|Region|
|Servercertificate|String|No|xxxxxx|Security certificate content. If the certificate is not enabled, the parameter is left blank. Enter the certificate content if any certificate is configured.|

## Return parameters {#section_nrn_yjl_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=SetDomainServerCertificate&DomainName=test.com&CertName=myCert1&ServerCertificateStatus=on&ServerCertificate=xxx&PrivateKey=yyy&public request parameter
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


