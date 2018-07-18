# What is Alibaba Cloud CDN? {#concept_aml_tlg_tdb .concept}

Alibaba Cloud Content Delivery Network \(CDN\) caches contents at physical nodes, then strategically delivers them to end users from the nearest node. It allows the users to efficiently acquire the resource they need, avoiding the possible network congestion, accelerating the user resource acquisition, and ensuring the user experience.

## How it works {#section_dsj_nlb_n2b .section}

Suppose that your origin site is in Hong Kong, and domain name www.a.com has access to CDN service. Here is what happens when a user in Beijing requests contents from your site.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/4886_en-US.png)

1.  A user in Beijing requests contents from your website or application \(with the domain name of www.a.com\).
2.  The LDNS routes the request to the best node \(here is Beijing Node 2.2.2.2\) in terms of shortest geographical distance to the user. \(Step 2-6 in the architecture above.\)
    -   LDNS resolutes www.a.com, then gets the response of CNAME \(www.a.tbcdn.com\).
    -   LDNS requests contents from Alibaba Scheduling System. The system then allocates and returns the most suitable node’s IP.
3.  The user requests contents from the routed node \(Beijing Node 2.2.2.2, Step 7-10 in the architecture above.\).
    -   If the contents have been cached in the Beijing Node, CDN directly returns them to the user.
    -   If the files are not in the cache, the Beijing Node requests the contents from the origin fetch. Upon the contents arriving, the Beijing Node forwards to user, in the light of his customized caching policy.

## Basic Concepts {#section_gh2_by2_l2b .section}

-   CNAME \(Canonical Name\): an alias for another domain name, which can be used to resolve a domain name to another domain name.

-   [Back-to-origin HOST](https://www.alibabacloud.com/help/doc-detail/73943.htm): You can customize a Web server domain name that a CDN node accesses in the back-to-origin process.

-   [Protocol-based origin retrieval request](https://www.alibabacloud.com/help/doc-detail/34949.htm): The same protocol is used for sending origin retrieval requests and accessing resources from the client.

-   [Filter parameters](https://www.alibabacloud.com/help/doc-detail/27128.htm): When a URL request includes a question mark \(?\) and request parameters are sent to a CDN node, the CDN node determines whether to send the request to the origin site.


## Operations {#section_i4g_cnf_l2b .section}

To quickly get started with CDN service, go to Quick Satrt. You can also check [CDN Learning Path](https://www.alibabacloud.com/getting-started/learningpath/cdn) to quickly get the full view of Alibaba Cloud CDN.

You can log on [CDN Console](https://cdn.console.aliyun.com) to experience all functions。

Moreover, you can check [API documentations](https://www.alibabacloud.com/help/doc-detail/27155.htm) to flexibly realize your business target.

## Price and billing {#section_cdg_yqb_n2b .section}

See [Pricing overview](https://www.alibabacloud.com/help/doc-detail/73877.htm) to quickly know how Alibaba Cloud CDN charges. Basic services and value-added services are the main two parts. You can choose PayByTraffic or PayByBandwidth for basic services.

For more information, see [Product Pricing](https://www.alibabacloud.com/product/cdn).

## Related services {#section_lpx_g3f_l2b .section}

[Dynamic Route for CDN](https://www.alibabacloud.com/help/product/64812.htm), distinguishing dynamic and static resources and accelerating them respectively.

[Object Storage Service \(OSS\)](https://www.alibabacloud.com/help/product/31815.htm), effectively improving website access speed and reducing the data charges that may incur on the external network.

[ApsaraVideo Live service](https://www.alibabacloud.com/help/product/29949.htm), delivering an integrated solution including media asset, slice transcoding, visiting authentication, content delivery acceleration.

[Alibaba Cloud DNS](https://www.alibabacloud.com/help/product/34269.htm), providing powerful but stable resolutions and dispatching service, ensuring smooth user visiting experience.

[Elastic Compute Service \(ECS\)](https://www.alibabacloud.com/help/product/25365.htm), enhancing the website availability, protecting the information on server's source station, and lowering the use cost of bandwidth.

[Server Load Balancer](ttps://www.alibabacloud.com/help/product/27537.htm), setting whose IP address as the source site, which relieves the bandwidth pressure.

