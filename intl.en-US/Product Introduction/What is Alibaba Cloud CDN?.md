# What is Alibaba Cloud CDN? {#concept_aml_tlg_tdb .concept}

Alibaba Cloud Content Delivery Network \(CDN\) caches contents at physical nodes, then strategically delivers them to end users. It allows the users to efficiently acquire the resources they need, avoids the possible network congestion, and enhances the user experience.

## How it works {#section_dsj_nlb_n2b .section}

Suppose that your origin site is in Hong Kong, and the domain name www.a.com has access to the CDN service. The following steps take place when a user in Beijing requests contents from your site.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/4886_en-US.png)

1.  A user in Beijing requests content from your website or application \(with the domain name of www.a.com\).
2.  The LDNS routes the request to the node that is the shortest geographical distance from the user \(steps 2 to 6 in the figure above\), which in this case is Beijing Node 2.2.2.2.
    -   LDNS resolves the domain name www.a.com, then gets the response of the CNAME \(www.a.tbcdn.com\).
    -   LDNS requests contents from Alibaba Scheduling System. The system then allocates and returns the most suitable node’s IP.
3.  The user requests content from the routed node, Beijing Node 2.2.2.2 \(steps 7 to 10 in the figure above\).
    -   If the content has been cached at the Beijing node, CDN directly delivers them to the user.
    -   If the files are not in the cache of the Beijing node, the node requests the content from the origin site. When the content is received, the Beijing node forwards to the user, in the light of his customized caching policy.

## Basic Concepts {#section_gh2_by2_l2b .section}

-   CNAME \(Canonical Name\): another domain name, which can be used to resolve a domain name to another domain name.

-   [Back-to-origin HOST](https://www.alibabacloud.com/help/doc-detail/73943.htm): You can customize a Web server domain name that a CDN node accesses in the back-to-origin process.

-   [Protocol-based origin retrieval request](https://www.alibabacloud.com/help/doc-detail/34949.htm): The same protocol is used for sending origin retrieval requests and accessing resources from the client.

-   [Filter parameters](https://www.alibabacloud.com/help/doc-detail/27128.htm): When a URL request includes a question mark \(?\) and request parameters are sent to a CDN node, the CDN node determines whether to send the request to the origin site.


## Operations {#section_i4g_cnf_l2b .section}

To get started with CDN, go to Quick Start. You can also follow the [CDN Learning Path](https://www.alibabacloud.com/getting-started/learningpath/cdn) to get a complete understanding of CDN.

You can log on [CDN Console](https://cdn.console.aliyun.com) to enjoy all functions.

Moreover, you can check [API documentations](https://www.alibabacloud.com/help/doc-detail/27155.htm) to flexibly realize your business targets.

## Price and billing {#section_cdg_yqb_n2b .section}

See [Pricing overview](https://www.alibabacloud.com/help/doc-detail/73877.htm) to quickly know how Alibaba Cloud CDN charges. Basic services and value-added services are the main two parts. You can choose PayByTraffic or PayByBandwidth for basic services.

For more information, see [Product Pricing](https://www.alibabacloud.com/product/cdn).

## Related services {#section_lpx_g3f_l2b .section}

[Dynamic Route for CDN](https://www.alibabacloud.com/help/product/64812.htm): Distinguishes dynamic and static resources and accelerates both separately.

[Object Storage Service \(OSS\)](https://www.alibabacloud.com/help/product/31815.htm): Improves website access speed and reduces the data charges that may be incurred on the external network.

[ApsaraVideo Live service](https://www.alibabacloud.com/help/product/29949.htm): Delivers an integrated solution including media asset, slice transcoding, visiting authentication, and content delivery acceleration.

[Alibaba Cloud DNS](https://www.alibabacloud.com/help/product/34269.htm): Provides powerful but stable resolutions and dispatches services, ensuring a smooth experience for visiting users.

[Elastic Compute Service \(ECS\)](https://www.alibabacloud.com/help/product/25365.htm): Enhances website availability, protects the information on a server’s source station, and lowers the cost of bandwidth use.

[Server Load Balancer](ttps://www.alibabacloud.com/help/product/27537.htm): Sets the server's IP address to the source site, which relieves the bandwidth pressure.

