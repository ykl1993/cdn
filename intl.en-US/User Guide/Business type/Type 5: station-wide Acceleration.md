# Type 5: Station-wide Acceleration {#concept_uw1_phk_xdb .concept}

## Introduction to application scenarios {#section_uwg_shk_xdb .section}

The whole station accelerated the integration of dynamic acceleration and static acceleration, and broke through the previous individual acceleration, with simple configuration, it is intelligent to distinguish between dynamic and static requests, and achieve the whole station acceleration. All-station acceleration for dynamic and static content mixing across industries, with more dynamic resource requests \(such as ASP, JSP\), PHP and other format files\) site:

-   Scenario 1: rich and complex dynamic content reduces page loading speed and affects user experience.
-   Scenario 2: single-line source stations, burst traffic, network congestion, and so on lead to page latency and content delivery failure.
-   Scenario 3: Game-like customers, dynamic content, real-time communication, high concurrency, traditional communication protocols do not meet performance requirements.
-   Scenario 4: The source station load distribution is uneven and the source station pressure caused by the burst visit.
-   Scenario 5: Domestic operators have a complex environment, the website has been hijacked, and the content of the site has been altered, using only the HTTP protocol for transmission may be at risk of dynamic content disclosure, more secure and efficient network links and content distribution are needed.

For each of the above scenarios, the Ali cloud CDN station-wide acceleration is provided:

-   The dynamic and dynamic separation is accelerated, and the dynamic content uses intelligent routing, transmission protocol optimization, and link reuse technology, static content uses edge caching to improve the loading speed of the entire station resource.
-   Real-Time Detection and smooth spanning technology stable and efficient handling of high-flow loads, providing all-day-to-day network availability.
-   Back-to-Back load balancing, multi-source primary provisioning, connection reuse and ordered back-to-back technology reduces source pressure and Failure risk.
-   All link HTTPS Security acceleration, anti-theft chain, IP flow limit, and so on, to ensure the security of the source station.
-   Customize set up static rules, cache rules, and have panoramic information monitoring and warning capabilities.

**Note:** The station-wide acceleration is the default pure dynamic acceleration, which means that all dynamic and static requests obtain resources through the optimal routed backsource, by configuring to specify a static file type or path, you can visually distinguish between dynamic and static resources, static resources cache on the edge node, dynamic resources use dynamic acceleration, to achieve the fastest acceleration effect.

## Operation Steps {#section_y2p_whk_xdb .section}

1.  Add a CDN domain name.

    Please refer to [Quick Start](../../../../reseller.en-US/Quick Start/Quick start.md#), be aware to select a business type of: All Station acceleration.

2.  Domain Name configuration.

    After the domain name is added, the whole site is accelerated using pure dynamic acceleration by default, you need to specify a static file by configuring the dynamic static acceleration rule, and the specified static file uses static acceleration, the cache is on the CDN node for better acceleration. The specific configuration methods are as follows:

    -   Dynamic static acceleration rule settings:

        -   [Static file type](reseller.en-US/User Guide/Value-added service/Dynamic Route for CDN/Static file type.md#)
        -   [Static URI settings](reseller.en-US/User Guide/Value-added service/Dynamic Route for CDN/Set Static File URI.md#)
        -   [Static path settings](reseller.en-US/User Guide/Value-added service/Dynamic Route for CDN/Static path settings.md#)
        -   [Special header settings](reseller.en-US/User Guide/Value-added service/Dynamic Route for CDN/Special header settings.md#)
        -   [Dynamic Protocol follows back Source](reseller.en-US/User Guide/Value-added service/Dynamic Route for CDN/Dynamic Protocol follows back Source.md#)
    -   Recommended Configuration:

        -   HTTPS Security acceleration, just upload the accelerated Domain Name Certificate/private key after you turn on secure acceleration mode, and supports viewing, disabling, enabling, editing of certificates to understand Certificate Format description.
        -   Access control related settings to ensure the distribution of content security, prevent chain theft or malicious requests from causing unnecessary loss of traffic.
            -   [Refer security chain](reseller.en-US/User Guide/Domain Names/Access Control Settings/Anti-leech.md#)
            -   [IP blacklist](reseller.en-US/User Guide/Domain Names/Access Control Settings/IP Blacklist and Whitelist.md#)
        -   Performance Optimization related settings, smart compression distribution, ignore URL parameters to increase cache hit ratio.
            -   [Page Optimization](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Page Optimization.md#)
            -   [Intelligent Compression](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Smart Compression.md#)
            -   [Filter parameters](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Filter Parameter.md#)
        -   For more features, browse the CDN features list.

## Billing rules {#section_lvt_b3k_xdb .section}

-   The CDN all-station accelerated billing item is the base cost + the requested number of charges. The base cost is the base cost based on the Peak bandwidth selected by the CDN service or the flow meter fee. The cost of the number of requests includes the number of dynamic HTTP requests, the number of dynamic HTTPS requests, and the number of static HTTPS requests, respectively according to the unit price on a daily basis.
-   For more details, please see the all-station accelerated billing rule.

