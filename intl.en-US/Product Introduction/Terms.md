# Terms {#concept_plh_jlc_5db .concept}

## Acceleration domain name {#section_obn_stb_p2b .section}

An acceleration domain name, specified by you, can be a website, an email address, or an FTP server. In Alibaba Cloud CDN documentation, acceleration domain name refers to domain name.

## Origin site {#section_dym_wtb_p2b .section}

The origin site is the server where your actual business and service is. Origin sites can be one of three types: OSS back-to-origin domain, IP, or custom.

## CNAME record {#section_cm2_nlc_5db .section}

A Canonical Name \(CNAME\), another domain name, can be used to resolve one domain name to another.

For example, a large amount of information is stored on your server, which can be accessed through `docs.example.com`. Now, you want to be able to access the same information through `documents.example.com` too. You can add a CNAME record at your DNS service provider, pointing`documents.example.com`to`docs.example.com`. Then, all requests to access `documents.example.com` are transferred to`docs.example.com`, giving access to the required information.

## CNAME domain name {#section_dm2_nlc_5db .section}

After you open CDN and add your domain name on Alibaba Cloud Console, you will receive a CNAME domain name, in the format `*.*kunlun*.com`. Then, you can add a CNAME record on your DNS provider, directing your acceleration domain name to the domain name `*.*kunlun*.com`. When the CNAME record is activated, DNS, all requests to access the acceleration name can be transferred to CDN nodes.

## SSL/TLS {#section_ujl_jwv_m2b .section}

SSL \(Secure Sockets Layer\) is a TCP-based secure communication protocol. It efficiently helps applications and software guarantee the completeness and security of data transfers over the Internet. TLS \(Transport Layer Security\) evolved to the SSL after standardization. As a result, SSL and TLS are collectively known as SSL/TLS.

## DNS {#section_em2_nlc_5db .section}

DNS stands for Domain Name System. It provides a domain name resolution service, converting a domain name to an IP address, so that it can be recognized by the network. People tend to remember domain names, while machines remember IP addresses. In fact, domain names and IP addresses are synonymous with each other. Domain name resolution requires a dedicated domain name resolution server, and runs automatically. For example, the domain name `[www.baidu.com](http://www.baidu.com/)`is automatically converted to the IP address `220.181.112.143`. You can use Alibaba Cloud DNS or other DNS products.

## Edge nodes {#section_fm2_nlc_5db .section}

In this document, the terms edge node, CDN node, cache node, acceleration node, and Alibaba Cloud node refer to Alibaba Cloud edge node, sometimes shortened to node. Edge nodes form a network of servers, and are located in areas across the globe. When a user requests content, the content is cached in the nearest edge node to the user, and then distributed to the user. In this way, edge nodes allow users to more efficiently acquire resources.

## Back-to-origin Host {#section_gm2_nlc_5db .section}

The origin site determines the IP address to which a back-to-origin request is sent. The Back-to-origin Host determines the specific site of the IP address to which a back-to-origin request is sent.

Example 1: The origin site is a domain name. If the origin site is`www.a.com` and the back-to-origin host is`www.b.com`, the actual back-to-origin request is sent to the IP address resolved from`www.a.com` corresponding to the site `www.b.com`on the host.

Example 2: The origin site is an IP address. If the origin site is1.1.1.1, and the back-to-origin host is `www.b.com`. Then, the actual origin retrieval request is sent to`www.b.com` on the host corresponding to 1.1.1.1.

## Back-to-Origin Protocol  {#section_hm2_nlc_5db .section}

The protocol used during a back-to-origin request is consistent with the protocol used when the user accesses the resource.

-   When an end user requests the resource by using HTTPS, CDN nodes will access the uncached resources from the origin site by also using HTTPS.
-   When an end user requests the resource by using HTTP, CDN nodes will access the uncached resources from the origin site by also using HTTP.

## Filter parameters {#section_im2_nlc_5db .section}

With Filter Parameter, you can control whether to filter out the section of a URL after the “?” \(question mark\) when caching contents to nodes based on your business needs.

-   If you enable this function, CDN nodes will filter out the part of the URL after the "?", then cache only one copy of each URL if the part of the URL before the “?” is the same.
-   If you disable the function, CDN nodes will cache a copy of each URL.

We recommend that you enable the Filter Parameter function if different parameters in your URL indicate the same content, which will efficiently improve the caching hit rate.

