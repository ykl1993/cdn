# DescribeCdnDomainDetail {#reference_crt_dny_5db .reference}

Obtain the basic information for the specified CDN domain name configuration.

## Request parameters {#section_cqh_sny_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|Describecdndomaindetail| The name of this interface. Value:

 DescribeCdnDomainDetail

 |
|DomainName|String|Yes|www.yourdomain.com| Domain name.

 |

## Return Parameters {#section_rkq_d4y_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74| Requestid.

 |
|GetDomainDetailModel| | | Domain name details.

 |
|└GmtCreated|String|2015-06-25T03:30:50Z| Creation time.

 |
|└GmtModified|String|2017-06-25T03:30:50Z| Recent modification time.

 |
|└ SourceType|String|domain| Source site type. Value meaning:

-   ipaddr indicates IP source site.
-   domain indicates domain name source site.
-   oss indicates the specified OSS Bucket is the source site.

 |
|└DomainStatus|String|online| The domain name status.

 |
|└SourcePort|Integer|80| The source port number.

 |
|└CdnType|String|web| The business type of CDN domain name. Value meaning:

-   web: the acceleration of images and small files. 
-   download: acceleration of large file downloads.
-   video: the acceleration of the audio and video on demand.
-   liveStream: the accerleration of the live streaming media.

 |
|└Cname|String|domain.w.alikunlun.net| The CNAME domain name generated for the CDN domain name. It is required to resolve the CNAME of the CDN domain name to this domain name at the DNS provider.

 |
|└HttpsCname|String|yourdomain.com.alikunlun.com| Activate the CNAME domain name of the https.

 |
|Doubledomainname|String|yourdomain.com| Domain name.

 |
|└Description|String|The live domain name.| Note.

 |
|└ServerCertificateStatus|String|on| Whether the ssl certificate is activated.

-   on indicates the certificate is activated.
-   off indicates the certificate is deactivated.

 |
|└ServerCertificate|String|——-BEGIN CERTIFICATE——-\\nMIxxxxxxxxx8LDVT2o=\\n——-END Certificate ---| If activated, this is the certificate public key.

 |
|└Region|String|cn-hangzhou| The unit information of the live domain name.

 |
|└Scope|String|domestic| Region.

 |
|└CertificateName|String|Certificate 1| The name of the certificate.

 |
|└ResourceGroupId|String|abcd1234abcd1234| The resource group ID.

 |
|└SourceModels| | | The source site information.

 |
|└Content|String|test.com| Source site address.

 |
|└Type|String|domain| The source site type. Value:

-   ipaddr: IP source site.
-   domain: the domain name source site.
-   oss: OSS Bucket is the source site.

 |
|└Port|Integer|80| Port that supports 443 and 80.

 |
|└Enabled|String|online| Status.

 |
|└Priority|String|20| Priority.

 |
|└Sources|String|Source site information.| \{ "Source": \[ "yourdomain.com" \] \}

 |

## Examples {#section_qbz_lqy_5db .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "GetDomainDetailModel":{
            "CdnType":"web",
            "Cname":"bb.test.com.w.kunlunle.com",
            "DomainName":"bb.test.com",
            "DomainStatus":"online",
            "GmtCreated":"2015-06-25T03:30:50Z",
            "GmtModified":"2015-06-25T03:30:53Z",
            "HttpsCname":"bb-test-com.alikunlun.com",
            "Region":"huadong",
            "ResourceGroupId":"abcd1234abcd1234",
            "Sourcemodels ":{
                "SourceModel":[{
                    "Content":"test.com",
                    "Enabled":"online",
                    "Port":80,
                    "Priority":"20",
                    "Type":"domain"
                
            
            "Sourcetype": "Domain ",
            "Sources":{
                "Source":["test.com"]
            
        
        "Requestid": "maid"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


