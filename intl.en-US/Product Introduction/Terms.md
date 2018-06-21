# Terms {#concept_plh_jlc_5db .concept}

## CNAME record {#section_cm2_nlc_5db .section}

A Canonical Name \(CNAME\) is an alias for another domain name, which can be used to resolve a domain name to another domain name. When the DNS system queries the name of the left side of the CNAME, it turns to the names of the right side of the CNAME for query again, and tracks to the last PTR or A name, and returns a result after query successfully. Otherwise, the query fails. For example, you have a server where a large amount of information is stored, you can use `docs.example.com`to access these resources, but hope to access them by using`documents.example.com`. Then you can add a CNAME record at your DNS service provider, to direct`documents.example.com`to`docs.example.com`. After adding the CNAME record, all requests to access `documents.example.com`are transferred to`docs.example.com` and can obtain the same content.

## CNAME domain name {#section_dm2_nlc_5db .section}

You will receive an accelerated domain name which is the CNAME domain name after CDN acceleration on the Alibaba Cloud console is configured\(This CNAME must be`*.*kunlun*.com`\). You must add CNAME record at your DNSservice provider, to direct your CDN domain name to the CNAME of `*.*kunlun*.com`, then all the request under your domain name are transferred to Alibaba Cloud CDN node to achive acceleartion effect.

## DNS {#section_em2_nlc_5db .section}

DNS stands for Domain Name System. It refers to the domain name resolution service. Its function on the Internet is to convert a domain name to an IP address that can be recognized by the network. People tend to remember domain names, while machine remember IP addresses. Domain names and IP addresses are synonymous to each other and the task of converting between the two is called domain name resolution. Domain name resolution requires a dedicated domain name resolution server to complete the task, and the entire process runs automatically. For example, the domain name`www.baidu.com`is automatically converted to `220.181.112.143`.

Common DNS service providers includes Alibaba Cloud DNS, www.net.cn, DNSPod, xinnet, oute53 \(AWS\), Dyn, and Cloudflare.

## Edge nodes {#section_fm2_nlc_5db .section}

In this document, edge node, CDN node, cache node, acceleration node or Alibaba Cloud node all refer to Alibaba Cloud edge node. Edge node is a concept proposed in contrast to the complex structure of the network. It refers to network nodes with a smaller number of accessible links. This improves the response capability and connection speed for the end user. Edge nodes are used to store webpage contents and objects with a higher traffic volume in specialized cache machine on the front-end of the server. This improves the speed and quality of website access.

## Origin retrieval host {#section_gm2_nlc_5db .section}

Origin retrieval host: The origin retrieval host determines the site to which a origin retrieval request is sent.

Example 1: The origin site is a domain name. If the origin site is`www.a.com` and the origin retrieval host is`www.b.com`,the actual origin retrieval request is sent to the IP address resolved from`www.a.com` corresponding to the site `www.b.com`on the host.

Example 2: The origin site is an IP address. If the origin site is1.1.1.1, and the origin retrieval host is `www.b.com`. Then, the actual origin retrieval request is sent to`www.a.com` on the host corresponding to 1.1.1.1.

## Protocol-based origin retrieval request {#section_hm2_nlc_5db .section}

The same protocol is used for sending origin retrieval requests and accessing resources from the client. That is, if the client initiates an HTTPS request for resources but the resources are not cached on the CDN node, the node initiates a origin retrieval HTTPS request for the resources. The same is true for HTTP requests.

## Filter parameters {#section_im2_nlc_5db .section}

When a URL request includes a question mark \(?\) and request parameters are sent to a CDN node, the CDN node determines whether to send the request to the origin site. If the "Filter Parameters" function is enabled, after the request arrives at the CDN node, the URL without parameters will be intercepted and requested against the origin site. In addition, the CDN node keeps only one copy. If the "Filter Parameters" function is disabled, different copies are cached on the CDN node for different URLs.

Example of use

Foe example, `http://www.abc.com/a.jpg?x=1`URL request is sent to a CDN node. After the**Filter Parameters**function is enabled, the CDN node initiates a request `http://www.abc.com/a.jpg` \(ignore the parameter x=1\) to the origin site. After the origin site returns a response, and the response goes to the CDN node, the CDN node keeps a copy, and then continues to respond to the terminal the content of `http://www.abc.com/a.jpg`. For all requests similar to `http://www.abc.com/a.jpg?`parameters, the origin site responds to the content of CDN copy `http://www.abc.com/a.jpg` . When the "Filter Parameter" function is disabled, different copies are cached on the CDN node for different URLs. For example: different contents are returned by the origin site in response to`http://www.abc.com/a.jpg?x=1` and `http://www.abc.com/a.jpg?x=2`.

