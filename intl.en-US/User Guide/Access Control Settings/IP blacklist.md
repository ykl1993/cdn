# IP blacklist {#concept_drs_1q2_xdb .concept}

## Introduction {#section_xsf_2q2_xdb .section}

CDN supports the blacklist rules. An IP address that is listed on the blacklist cannot access the corresponding domain.

## Attentions: {#section_odl_2q2_xdb .section}

You can use an IP network segment to add IP addresses to the blacklist.

**Note:**  For example, 127.0.0.1/24. 24 indicates that the first 24 bits in the subnet mask are used as effective bits, for example, 32-24=8 bits are used to express host numbers. In this way, the subnet can accommodate 2 ^ 8-2 = 254 hosts. And 127.0.0.1/24   indicates the IP network segment scope of 127.0.0.1~127.0.0.255.

## Procedure {#section_i1n_2q2_xdb .section}

Enter the CDN domain name overview page, go to Domain Names page, select the domain name that you want to set up, and click**Configure**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5153/3469_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5153/3470_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5153/3471_en-US.png)

