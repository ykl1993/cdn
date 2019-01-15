# Quick start {#concept_nwf_psv_tdb .concept}

This document describes how to quickly get started with the CDN service. The procedure is as follows:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5111/15475458876046_en-US.png)

## Step 1. Enable the CDN service {#section_fyr_1tv_tdb .section}

1.  Go to the Alibaba Cloud website, and quickly learn about the product in the [CDN Product Details Page](https://www.alibabacloud.com/product/cdn?spm=a2c63.m28257.1097650.dznavproductsb3.2d10ed692Mw3yo). Then click  **Buy Now**.
2.  On the order page, select an appropriate [billing method](https://www.alibabacloud.com/product/cdn/pricing?). Once you confirm the order, the CDN service is enabled.  And you can access the domain name you want to accelerate.

## Step 2. Add a CDN domain name {#section_rqh_15v_tdb .section}

1.  Add a domain name.

    Go to the [CDN console](https://cdn.console.aliyun.com), select **Domain Names**. You can view all the CDN domain names and status that you have added. Click **Add Domain Name**

2.  Enter the basic information.

    Enter the CDN domain name \(typically a subdomain name or a wildcard domain name is used, for example `cdntest.example.com`\), and select an appropriate business type and origin site. Click **Next** to wait for the reviewing.

    **Note:** Using Alibaba Cloud ECS or OSS as your origin site will accelerate your domain name verification.

    CDN domain name Description:

    -   Wildcard domain acceleration is supported. Chinese domain acceleration is not supported. Note this rule when you enter wildcard domains: `*.test.com`. For more information, see Wildcard Domain Acceleration Rules
    -   A CDN domain cannot added multiple times. If you encounter a **Domain already added** issue, submit a ticket to us for help.
    -   Up to 50 CDN domains can be added under one account.
    -   The domain content must comply with CDN specifications. For more information, see [CDN Service Use Restrictions](../../../../../intl.en-US/Product Introduction/Limits.md#).
    Business type description:

    The Alibaba Cloud CDN scheduling system performs specific scheduling optimization based on the different types of business selected by the user:

    |Business type|Note|
    |:------------|:---|
    |[Images and small files](../../../../../intl.en-US/User Guide/Business type/Type 1: Images And Small Files Acceleration.md#)|If the content to be accelerated is mostly images and web files \(For example, small files, images and web-styled file\), we recommend that you select the "images and small files" business type.|
    |[Large file downloads](../../../../../intl.en-US/User Guide/Business type/Type 2: Large file downloads acceleration.md#)|If the content to be accelerated is large files \(static files larger than 20 MB\), for example, games installation package, application update, mobile ROM update, application program package download and other scenarios, acceleration of **large file downloads** is recommended.|
    |[On-demand video/audio](../../../../../intl.en-US/User Guide/Business type/Type 3: On-demand video__audio acceleration.md#)|For large video files, acceleration of live streaming media is recommended to accelerate video on demand and live streaming services.|
    |[Live streaming media](../../../../../intl.en-US/User Guide/Business type/Type 4: Live Streaming Media Acceleration.md#)|Currently, live streaming has been an independent product. Refer to [ApsaraVideo Live](https://www.alibabacloud.com/product/apsaravideo-for-live) for more information.|
    |[Dynamic Route for CDN](../../../../../intl.en-US/User Guide/Business type/Type 5: Dynamic Route for  CDN.md#)|Currently, Dynamic Route for CDN has been an independent product. Refer to the [Dynamic Route for CDN](https://www.alibabacloud.com/product/dcdn) for more information.|

    Types of origin sites:

    |Origin site type|Description|
    |:---------------|:----------|
    |IP|You can enter multiple the Internet server IPs. Alibaba Cloud ECS IP can be unaudited.|
    |Origin server domain name|Supports multiple origin server domain names.**Note:** The origin server address you entered cannot be the same as the CDN domain name. Otherwise, it leads to cycling resolution, and cannot be returned to the origin server. For example, if your CDN domain name is img.yourdomain.com, we recommend that you set your origin server as cdn.yourdomain.com.

|
    |OSS|Enter the Internet domain name of Alibaba Cloud OSS bucket. For example, xxx.oss-cn-hangzhou.aliyuncs.com. You can view the Internet domain name of OSS on OSS console. You can also directly select the OSS bucket under the same account.|

    **Note:** SNI is not supported for CDN back-to-origin requests.

    Acceleration region description:

    -   Select the acceleration region based on your needs: Mainland China, overseas only \(domestic nodes unavailable\), or world-wide.
    -   L3 and above members can apply for this feature by submitting a ticket.
    -   Traffic generated from overseas nodes incurs a higher cost than that from domestic nodes. For more information, see [Purchase Guide](https://www.alibabacloud.com/product/cdn/pricing?).
    -   If you select overseas acceleration only, the registration at China's Ministry of Industry and Information Technology is not required.
3.  Click **Next**, then wait for review.

    **Note:** 

    -   You can submit a ticket if you have an urgent requirement for review.
    -   If your origin site is Alibaba Cloud ECS or OSS, you will finish reviewing faster.
4.  Complete adding domain name.

    After the CDN domain name reviewing is completed, it displays in **Domain Names**, and the status **Running** indicates it has been added successfully.

    **Note:** After adding the CDN domain name, Alibaba Cloud CDN assigns you the corresponding cname address, you must  configure cname for the CDN service to take effect. See the following Step 3.


## Step 3. Configure CNAME {#section_efx_nzv_tdb .section}

1.  Copy the CNAME address assigned by the system from the domain name list in **Domain Names** in the CDN console:
2.  Go to the DNS console of your DNS service provider \(for example, www.net.cn, Alibaba Cloud DNS, DNSPod, xinnet. Tencent DNS, route53 and godaddy\) to add the cname record. Examples of the following service providers are provided: [Configure Alibaba Cloud DNS](intl.en-US//Configure CNAME by Alibaba Cloud DNS.md#).

## Step 4. Verify if CNAME is enabled for the domain name {#section_g4d_jzc_b2b .section}

After you configure the CNAME record, the CNAME record may take a variable period of time to take effect, depending on your DNS provider.

You can `ping` or `dig` If the cname you added is resolved to`*.*kunlun*.com`, it indicates the CNAME configuration takes effect, and the CDN service is enabled.

