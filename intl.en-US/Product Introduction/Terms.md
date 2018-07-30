# Terms {#concept_plh_jlc_5db .concept}

## Acceleration domain name {#section_obn_stb_p2b .section}

An acceleration domain name, provided by your side for CDN acceleration, can be a website, an email address, or an FTP server. In Alibaba Cloud documentation for CDN, acceleration domain name refers to domain name.

## Origin site {#section_dym_wtb_p2b .section}

The server where the your real business and service is. The origin site has three types for option: OSS back-to-origin domain, IP, or custom.

## CNAME record {#section_cm2_nlc_5db .section}

A Canonical Name \(CNAME\), another domain name, can be used to resolve a domain name to another.

For example, a large amount of information is stored in your server, which can be accessed by using `docs.example.com`. Now, you wish to access to the information by using`documents.example.com` also. You can add a CNAME record at your DNS service provider, pointing`documents.example.com`to`docs.example.com`. Then, all requests to access `documents.example.com`are transferred to`docs.example.com`, being able to obtain the same information.

## CNAME domain name {#section_dm2_nlc_5db .section}

You will receive an acceleration domain name which is the CNAME domain name after CDN acceleration on the Alibaba Cloud console is configured \(This CNAME must be`*.*kunlun*.com`\). You must add CNAME record at your DNS service provider, to direct your CDN domain name to the CNAME of `*.*kunlun*.com`, then all the request under your domain name are transferred to Alibaba Cloud CDN node to achive acceleartion effect.

## SSL/TLS {#section_ujl_jwv_m2b .section}

SSL \(Secure Sockets Layer\) is a TCP-based secure communication protocol. It efficiently helps applications and software guarantee the completeness and security of the materials during transferring via internet. TLS \(Transport Layer Security\) is to the SSL after standardization. As a result, SSL and TLS are always seen as SSL/TLS together.

## DNS {#section_em2_nlc_5db .section}

DNS stands for Domain Name System. It provides domain name resolution service, converting a domain name to an IP address, so that it can be recognized by the network. People tend to remember domain names, while machine remember IP addresses. In fact, domain names and IP addresses are synonymous to each other. Domain name resolution requires a dedicated domain name resolution server, and runs automatically. For example, the domain name`www.baidu.com`is automatically converted to `220.181.112.143`. You can use Alibaba Cloud DNS or other DNS products.

## Edge nodes {#section_fm2_nlc_5db .section}

In this document, terms of edge node, CDN node, cache node, acceleration node or Alibaba Cloud node refer to Alibaba Cloud edge node, and can be short for node. Edge node is a concept proposed against the complex-structured network. It refers to network nodes with less accessible links towards the end users, which improves the response capability and connection speed. As contents are cached to all these node servers, the access experience for end users will be significantly improved.

## Back-to-origin Host {#section_gm2_nlc_5db .section}

The origin site determines the IP to which a back-to-origin request is sent, while Back-to-origin Host determines the site to which a back-to-origin request is sent.

Example 1: The origin site is a domain name. If the origin site is`www.a.com` and the back-to-origin host is`www.b.com`, the actual back-to-origin request is sent to the IP address resolved from`www.a.com` corresponding to the site `www.b.com`on the host.

Example 2: The origin site is an IP address. If the origin site is1.1.1.1, and the back-to-origin host is `www.b.com`. Then, the actual origin retrieval request is sent to`www.a.com` on the host corresponding to 1.1.1.1.

## Back-to-Origin Protocol  {#section_hm2_nlc_5db .section}

The protocol used during back-to-origin is consistent with the protocol used when the end user accessing the resource.

-   When an end user requesting the resource by using HTTPS, CDN nodes will access the uncached resources from the origin site by using HTTPS also.
-   When an end user requesting the resource by using HTTP, CDN nodes will access the uncached resources from the origin site by using HTTP also.

## Filter parameters {#section_im2_nlc_5db .section}

With the switch of Filter Parameters, you can control whether to filter the parameters after the "?" mark when caching contents to nodes based on your business need.

-   If you enable the function, CDN nodes will filter out the part after "?", then cache only one copy if the URLs share the same part before "?".
-   If you disable the function, CDN nodes will cache each URL's copy.

We recommend that you enable the Filter Parameter function if different parameters in your URL indicate the same content, which will efficiently improve the caching hit rate.

