# Set Priorities of Multiple Origin Sites and Custom Port {#concept_y1p_lcy_wdb .concept}

## Set priorities of multiple origin sites {#section_oxf_ncy_wdb .section}

Function overview

Alibaba Cloud CDN supports three types of back-to-source domain names: OSS back-to-source domain name, IP address, and custom domain name.  Multiple IP addresses and custom domain names are supported, and back-to-source priority can be configured when multiple origin sites exist.

When the back-to-source type is IP address or custom domain name, multiple origin sites are allowed and their priorities are configurable.   When multiple origin sites are added, the site priority is "main" and "standby ",  and the priority is "main"\> "standby ".

All back-to-source traffic is preferentially directed to higher-priority origin sites. If an origin site fails the health check for three consecutive times, all traffic is directed to lower-priority origin sites. If the origin site passes the health check, it is marked as available again and restored to its the original priority.  When all origin sites have the same back-to-source priority, CDN round-robin takes place.

Origin site health check: 4-layer health check is automatically performed on origin sites every 5 seconds.

Main supported scenario: Master/Slave origin site switch

Procedures

Go to the CDN domain name management list and select a domain name to go to the corresponding configuration page. The **multi-source priority function**  can be configured in the back-to-source settings.

1.  Click **Modify** in the Domain Name List and enable the origin Site setting function on the domain name configuration page.  
2.  Set **back-to-source origin sites** and ** priorities**.
    -   If you set your Origin site information to**IP** or **Origin Site**, pay as the internet-caused traffic.
    -   If you set your Origin site information to**OSS domain** , pay as the intranet-caused traffic. OSS Pricing Details. [OSS Pricing Details](https://www.alibabacloud.com/zh/product/oss?spm=a2796.7960336.224002.50.17815179w6xyJ3#pricing).
    -   If you have set an OSS domain name for your **origin site**, still pay as the intranet-caused traffic.
3.  Click**OK** to complete the configuration.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5142/3276_en-US.png)

    Now you can set the Back-to-Source port to Port 80, Port 443, or Custom.

    **Note:** 

    -   Multi-source priority setting is only applicable to the IP address type and origin-site domain name type, but is not applicable to the OSS domain name type. You can select appropriate origin site types and set the reasonable priorities based on your needs.
    -   Origin site setting is not applicable to acceleration of live video streaming.

## Set Custom Port {#section_xn5_pdy_wdb .section}

You can set custom port after enabling the white list.  The port number must be between 0 and 65535.

-   You cannot set custom port when your static or dynamic protocal is set to **Follow**.
-   Make sure that your back-to-source protocol and custom port are properly in use if you wish to set your back-to-source protocol to**Follow**by using OpenAPI.
-   Your back-to-source method will always follow the protocol \(**HTTP**or**HTTPS**\) and custom port you have set by using port, no matter what you have set in console.

