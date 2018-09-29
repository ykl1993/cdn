# What is Alibaba Cloud CDN? {#concept_aml_tlg_tdb .concept}

Alibaba Cloud Content Delivery Network \(CDN\) caches contents at physical nodes, then strategically delivers them to end users. It allows the users to efficiently acquire the resources they need, avoids the possible network congestion, and enhances the user experience.

## How it works {#section_dsj_nlb_n2b .section}

Suppose that your origin site is in Hong Kong, and the domain name www.a.com has access to the CDN service. The following steps take place when a user in Beijing requests contents from your site.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/15382038564886_en-US.png)

1.  A user in Beijing requests content from your website or application \(with the domain name of www.a.com\).
2.  The LDNS routes the request to the node that is the shortest geographical distance from the user \(steps 2 to 6 in the figure above\), which in this case is Beijing Node 2.2.2.2.
    -   LDNS resolves the domain name www.a.com, then gets the response of the CNAME \(www.a.tbcdn.com\).
    -   LDNS requests contents from Alibaba Scheduling System. The system then allocates and returns the most suitable node’s IP.
3.  The user requests content from the routed node, Beijing Node 2.2.2.2 \(steps 7 to 10 in the figure above\).
    -   If the content has been cached at the Beijing node, CDN directly delivers them to the user.
    -   If the files are not in the cache of the Beijing node, the node requests the content from the origin site. When the content is received, the Beijing node forwards to the user, in the light of his customized caching policy.

## Operations {#section_hb5_xrn_hfb .section}

You can log on [CDN Console](https://partners-intl.console.aliyun.com/#/cdn) to enjoy all functions.

Moreover, you can check [API documentations](https://www.alibabacloud.com/help/doc-detail/27155.htm) to flexibly realize your business targets.

## Related services {#section_ehy_4sn_hfb .section}

[Object Storage Service \(OSS\)](https://partners-intl.aliyun.com/help/product/31815.htm): Improves website access speed and reduces the data charges that may be incurred on the external network.

[ApsaraVideo Live service](https://partners-intl.aliyun.com/help/product/29949.htm): Delivers an integrated solution including media asset, slice transcoding, visiting authentication, and content delivery acceleration.

[Alibaba Cloud DNS](https://partners-intl.aliyun.com/help/product/34269.htm): Provides powerful but stable resolutions and dispatches services, ensuring a smooth experience for visiting users.

[Elastic Compute Service \(ECS\)](https://partners-intl.aliyun.com/help/product/25365.htm): Enhances website availability, protects the information on a server’s source station, and lowers the cost of bandwidth use.

[Server Load Balancer](https://partners-intl.aliyun.com/help/product/27537.htm): Sets the server's IP address to the source site, which relieves the bandwidth pressure.

