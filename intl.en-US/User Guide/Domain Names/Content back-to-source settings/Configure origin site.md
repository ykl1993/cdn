# Configure origin site {#concept_y1p_lcy_wdb .concept}

In this document, you can get abreast of what is origin site and custom port, and how to configure them.

## Introduction {#section_oxf_ncy_wdb .section}

Alibaba Cloud CDN supports three types of back-to-origin domain names: OSS back-to-origin domain name, IP address, and custom domain name. Multiple IP addresses and custom domain names are supported, and back-to-origin priority can be configured when multiple origin sites exist.

When the back-to-origin type is IP address or custom domain name, multiple origin sites are allowed and their priorities are configurable. When multiple origin sites are added, the site priority is "main" and "backup", and the priority is "main"\> "backup".

All back-to-origin traffic is preferentially directed to higher-priority origin sites. If an origin site fails the health check for three consecutive times, all traffic is directed to lower-priority origin sites. If the origin site passes the health check, it is marked as available again and restored to its the original priority. When all origin sites have the same back-to-origin priority, CDN round-robin takes place.

Origin site health check: 4-layer health check is automatically performed on origin sites every 2.5 seconds.

Main supported scenario: Master/Slave origin site switch.

## Procedure {#section_tn1_wfr_n2b .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  Go to **Basic configuration** \> **Origin site info****Origin Site Configuration**, set origin site types, address, and port. \(Now you can set the back-to-origin port to Port 80, Port 443, or Custom.\)
    -   If you set your Origin site information to **IP** or **Origin Site**, pay as the internet-caused traffic.
    -   If you set your Origin site information to**OSS domain**, pay as the intranet-caused traffic. [OSS Pricing Details](https://www.alibabacloud.com/zh/product/oss?spm=a2796.7960336.224002.50.17815179w6xyJ3#pricing).
    -   If you have set an OSS domain name for your **origin site**, still pay as the intranet-caused traffic.
3.  Click **OK** to complete the configuration.

    **Note:** 

    -   Multi-source priority setting is only applicable to the IP address type and origin-site domain name type, but is not applicable to the OSS domain name type. You can select appropriate origin site types and set the reasonable priorities based on your needs.
    -   Origin site setting is not applicable to acceleration of live video streaming.

## Set Custom Port {#section_xn5_pdy_wdb .section}

You can set custom port after enabling the white list.  The port number must be between 0 and 65535.

-   You cannot set custom port when your static or dynamic protocol is set to **Follow**.
-   Make sure that your back-to-origin protocol and custom port are properly in use if you want to set your back-to-origin protocol to **Follow** by using OpenAPI.
-   Your back-to-origin method will always follow the protocol \(**HTTP** or **HTTPS**\) and custom port you have set by using port, no matter what you have set in console.

