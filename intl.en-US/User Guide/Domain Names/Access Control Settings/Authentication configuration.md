# Authentication configuration {#concept_rtr_qsm_j2b .concept}

The URL authentication feature is designed to protect user's origin server resources from unauthorized downloading and misappropriation. Referer blacklist and whitelist with anti-leech can protect video content from some leeching attacks too some degree. However, it cannot completely protect site resources, as the referer contents can be forged. As a result, it is a more secure and effective way to protect your resources by using URL authentication.

## How it works {#section_jhh_cj2_xdb .section}

URL authentication uses Alibaba Cloud CDN nodes together with client resource sites to provide more secure and reliable anti-leech protection for origin site resources.

1.  The CDN client site provides an encrypted URL including verification information of permissions.
2.  You use the encrypted URL to initiate a request to the CDN node.
3.  The accelerated node authenticates the permission information in the encrypted URL to determine the legitimacy of the request. A normal response to a legitimate request will reject an illegal request.

## Authentication method {#section_zqg_dj2_xdb .section}

Alibaba Cloud CDN supports 3 authentication methods: A, B, and C. You can choose the authentication method based on your business need, so that it will help protect your origin site.

## Sample authentication code {#section_h25_k42_xdb .section}

You can check [Sample authentication code](reseller.en-US/User Guide/Domain Names/Access Control Settings/Sample authentication code.md#).

## Procedure {#section_n5x_l42_xdb .section}

1.  Go to the CDN console. Go to the **Domain Names** page, then select the target domain name. Click **Manage**.
2.  In the **Access Control** \> **Authentication Configuration** label, click **Modify**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15390/154345321610073_en-US.png)
3.  Switch on **Authentication**, choose Authentication **type**, and enter **Main Key** and **Backup Key**.
4.  Click **Confirm**.

