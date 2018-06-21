# What is CDN? {#concept_aml_tlg_tdb .concept}

## Introduction {#section_q3c_wn2_zdb .section}

Alibaba Cloud Content Delivery Network \(CDN\), clustered by edge node servers across regions, is a distributed network built on and overlaying the bearer network. It renovates the data transmission mode traditionally centered on web servers.

As a precise dispatching system, Alibaba Cloud CDN caches the source content to edge nodes, and distributes the user requests to the ideal nodes. It allows the users to efficiently acquire the resource they need, avoiding the possible network congestion, accelerating the user resource acquisition, and ensuring the user experience. To quickly get access to CDN service, go to [Quick Start](../../../../intl.en-US/Quick Start/Quick start.md#).

## The process for http request processing after using CDN is as follows: {#section_r3c_wn2_zdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/4886_en-US.png)

## Features {#section_k2l_pp2_zdb .section}

Intelligent node cache

-   Precise cache, delivering layer-based hot resource caching and more efficient resource acquisition.

-   High-speed cache, with multi-core CPU processing ability, efficiently using and controlling the RAM and maximizing SSD IOPS and throughput.

-   High-speed SSD processing with SSD acceleration for each node, greatly saving time for users and improving the availability.

-   Intelligent compression, effectively shrinking the transmitting content and accelerating the distribution.

-   UI optimization, minimizing the page sizes by removing the redundant on-page contents, and combining multiple JavaScript/CSS files into a single request.


Precise dispatching

-   Full-covered: It is applicable for wide arrays of websites and apps with targeted service support and all-round acceleration.

-   Million-level: It allows dispatching million-level domain names using a single server.

-   Controllable and scalable: It reduces the real cost.

-   Multi-system collaborated: 

-   It allows collaboration with security defense system, refresh system, and content management system.

-   Real-time: It supports node-level data-based estimation, improving the dispatching quality and accuracy.


Multi-scenario application

Seamlessly collaborated with various Alibaba Cloud services, CDN speeds up cloud resource accessing and downloading, including:

-   ApsaraVideo Live service, delivering an integrated solution including media asset, slice transcoding, visiting authentication, content delivery acceleration.
-   On-demand video service, enabling users to view on-demand videos smoothly. It supports mp4, flv, and other formats.
-   Object Storage Service \(OSS\), effectively improving website access speed and reducing the data charges that may incur on the external network.
-   Elastic Compute Service \(ECS\), enhancing the website availability, protecting the information on server's source station, and lowering the use cost of bandwidth.
-   Resource link authentication, enabling you to customize authentication keys, which ensures the security of your media asset.
-   Server Load Balancer, set whose IP address as the source site, relieving the bandwidth pressure.

CDN also allows non-Alibaba Cloud source stations to rapidly deploy the acceleration services just after resource verification.

Self management

-   Self-service console, allowing customized, intelligent, and minute-level deployment on all CDN nodes.

-   CDN Quick Start, enabling you to add, delete, modify, and query the domain names, set information such as accelerated node caching strategy, anti-leech, and optionally open acceleration service based on your individual demands via the console.

-   Open and scalable APIs, enabling flexible deployment, fast operations, precision usage, and timely monitoring of CDN domains, distribution resources, and monitoring data.  It can also works with the APIs of other Alibaba Cloud products for a custom, multi-platform portal. 


Real-time monitoring

-   All-round monitoring, including bandwidth, visiting quality, visitor data, hot analysis, and security guarding.

-   Multi-dimensional data analysis

-   Convenient resource report downloading


