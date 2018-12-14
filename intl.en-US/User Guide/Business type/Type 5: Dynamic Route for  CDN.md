# Type 5: Dynamic Route for CDN {#concept_uw1_phk_xdb .concept}

Now, this service has been an independent product:[Alibaba Cloud Dynamic Route for CDN](https://www.alibabacloud.com/product/dcdn?).

## Introduction to application scenarios {#section_uwg_shk_xdb .section}

The whole station accelerated the integration of dynamic acceleration and static acceleration, and broke through the previous individual acceleration, with simple configuration, it is intelligent to distinguish between dynamic and static requests, and achieve the whole station acceleration. All-station acceleration for dynamic and static content mixing across industries, with more dynamic resource requests \(such as ASP, JSP\), PHP and other format files\) site:

-   Scenario 1: rich and complex dynamic content reduces page loading speed and affects user experience.
-   Scenario 2: single-line source stations, burst traffic, network congestion, and so on lead to page latency and content delivery failure.
-   Scenario 3: Game-like customers, dynamic content, real-time communication, high concurrency, traditional communication protocols do not meet performance requirements.
-   Scenario 4: The source station load distribution is uneven and the source station pressure caused by the burst visit.
-   Scenario 5: Domestic operators have a complex environment, the website has been hijacked, and the content of the site has been altered, using only the HTTP protocol for transmission may be at risk of dynamic content disclosure, more secure and efficient network links and content distribution are needed.

## Features {#section_qhn_3m5_cgb .section}

For each of the above scenarios, the Ali cloud CDN station-wide acceleration is provided:

-   The dynamic and dynamic separation is accelerated, and the dynamic content uses intelligent routing, transmission protocol optimization, and link reuse technology, static content uses edge caching to improve the loading speed of the entire station resource.
-   Real-Time Detection and smooth spanning technology stable and efficient handling of high-flow loads, providing all-day-to-day network availability.
-   Back-to-Back load balancing, multi-source primary provisioning, connection reuse and ordered back-to-back technology reduces source pressure and Failure risk.
-   All link HTTPS Security acceleration, anti-theft chain, IP flow limit, and so on, to ensure the security of the source station.
-   Customize set up static rules, cache rules, and have panoramic information monitoring and warning capabilities.

**Note:** By default, all dynamic and static requests obtain resources through the optimal routed backsource, by configuring to specify a static file type or path, you can visually distinguish between dynamic and static resources, static resources cache on the edge node, dynamic resources use dynamic acceleration, to achieve the fastest acceleration effect.

