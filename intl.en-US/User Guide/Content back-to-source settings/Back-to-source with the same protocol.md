# Back-to-source with the same protocol {#concept_j1v_l1d_xdb .concept}

## Introduction {#section_hn2_q1d_xdb .section}

When the back-to-source with the same protocol feature is enabled, back-to-source requests for resources uses the same protocol used by the client in order to request resources. If the client makes an HTTPS request for resources, but the resources are not cached on the node, the same back-to-source HTTPS request will be made for resources.  This protocol is also applicable for HTTP requests.

**Note:** The origin site must support both the port 80 and port 443; otherwise, the back-to-source may fail.

## Procedure {#section_ihg_t1d_xdb .section}

Go to the Domain Names page, select a domain to enter the management page. You can enable or disable**Use the same protocol as the back-to-source protocol**function in back-to-source settings. 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5144/3343_en-US.png)

