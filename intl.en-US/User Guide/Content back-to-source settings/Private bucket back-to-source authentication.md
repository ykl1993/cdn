# Private bucket back-to-source authentication {#concept_ljh_42y_wdb .concept}

## Function overview {#section_zvk_bxc_xdb .section}

Private bucket back-to-source authentication is performed when traffic of a CDN domain is diverted to the bucket marked as private under a user account. After authentication is successful and authentication configuration is enabled, domain names enabled with private bucket authentication have the permission to access the private bucket.

**Note:** 

-   After authentication is successful and the private bucket function of corresponding domains are enabled, the CDN domain can be used to access the resource content in your private bucket. Consider carefully when you decide whether to enable this function. If the content in the private bucket to be authorized is not suitable to function as the back-to-source content of the CDN domain, do not perform authorization or enable the function.
-   You can use functions such as the referer anti-leech protection and authorization provided by CDN to protect resource security.
-   If your website faces attack risks, please buy Anti-DDoS service and do not perform authorization or enable the private bucket function.

## Configuration instructions {#section_qrl_jxc_xdb .section}

How to enable private bucket back-to-source authorization

1.  Choose Domain Name Configuration \> **Origin Site Configuration, ** \> **Private Bucket Authorization**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3335_en-US.png)

2.  Click **Authorize Now**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3336_en-US.png)

3.  Authorization is successful. Enable private bucket back-to-source configuration for the domain and click **Confirm**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3337_en-US.png)

4.  Succeed.

How to disable private bucket back-to-source authorization

1.  Choose **Access Control** \> **Role Management**.
2.  Delete AliyunCDNAccessingPrivateOSSRole authorization.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3338_en-US.png)

3.  Private bucket authorization is successfully deleted.

**Note:** If your CDN domain is sending back-to-source requests with the private bucket as the origin site, do not disable or delete private bucket authorization.

