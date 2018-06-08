# Set httpDNS {#concept_nj3_qmx_wdb .concept}

## Introduction {#section_o2w_smx_wdb .section}

-   A traditional DNS resolution is implemented by accessing the local DNS of a carrier in order to obtain the resolution result. However, this action can easily allow for DNS hijacking, DNS errors, and inter-network traffics, and lead to slowed, or failed, website access.
-   httpDNS is a DNS service that uses HTTP protocol to directly access the Alibaba Cloud CDN server. Because it bypasses the carrier’s local  DNS, it can avoid DNS hijacking and obtain real-time accurate DNS resolution results.
-   Principle:  initiate a request to access a designated Alibaba Cloud CDN httpDNS server through HTTP protocol. The httpDNS server performs domain resolution based on second-level DNS nodes distributed everywhere, obtains the domain name resolution result, and returns the result.

## httpDNS interface {#section_vm2_zmx_wdb .section}

Direct access through an HTTP interface is supported. The access method is as follows.

1.  Service URL

    ```
    http://umc.danuoyi.alicdn.com/multi_dns_resolve
    ```

2.  Request method:`POST`
3.  Supported parameter: `client_ip=x.x.x.x`. This parameter can be ignored if the IP address of the client initiating the httpDNS request is used.
4.  Request example: Multiple domains to be resolved are placed in the body of a POST request and are separated by whitespaces \(blank spaces, TABs, newline characters\).

    ```
    #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=182.92.253.16
    ' -d 'd.tv.taobao.com'
    ```

5.  Returned format: json data is returned. After resolution, domain IP addresses are extracted and polling can be performed among them. TTL cache and expiration rules must be followed.

    ```
    {"dns":[{"host":"d.tv.taobao.com","ips":[{"ip":"115.238.23.240","spdy":0},{"ip":"115.238.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
    ```

6.  Request example with multiple domains
    -   Request example

        ```
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=182.92.253.16
        ' -d 'd.tv.taobao.com vmtstvcdn.alicdn.com'
        ```

    -   Return example

        ```
        {"dns":[{"host":"vmtstvcdn.alicdn.com","ips":[{"ip":"115.238.23.250","spdy":0},{"ip":"115.238.23.240","spdy":0}],"ttl":300,"port":80},{"host":"d.tv.taobao.com","ips":[{"ip":"115.238.23.240","spdy":0},{"ip":"115.238.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```


