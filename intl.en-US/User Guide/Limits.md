# Limits {#concept_um5_wdx_wdb .concept}

## Restrictions on the use of CDN {#section_zhn_q2x_wdb .section}

Procedure

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5117/15438273483166_en-US.png)

1.  Real-name registration must be performed for accounts on the Alibaba Cloud official website.
2.  A CDN domain must have an [ICP license](https://beian.aliyun.com/?spm=5176.8142029.388261.3.a0SCC3) and be connected to Alibaba Cloud.
3.  The origin site content of a CDN domain must be stored on Elastic Compute Service \(ECS\) or Object Storage Service \(OSS\).  If the origin site content is not stored on Alibaba Cloud, access must be reviewed.

## Restriction {#section_r1h_lgx_wdb .section}

|Quantity|Limit quantity|
|:-------|:-------------|
|Quantity|Limit quantity|
|Domain Name|The maximum number of CDN domains for each Alibaba Cloud account is **20** . |
|IP origin site|The maximum number of IP origin sites for each CDN domain is **10**.|
|Cache refresh and push operations|**refresh:**2000items/day/account. **Directory refresh:**100100 items/day/account.|

If you have a large number of domain name acceleration needs, submit a ticket for special support.

## CDN domain name reclaiming rules {#section_p3p_qgx_wdb .section}

|If your CDN domain name...|The system will...|To continue using CDN acceleration, you must...|
|:-------------------------|:-----------------|:----------------------------------------------|
|not access traffic for more than 90 days \(including "normal operation"\)|Automatically deactivate the domain name to save the CDN domain name related records|Enable  CDN domain names.|
|Is in the disabled state for more than 120 days \(including auditing failed\)|Automatically delete the domain name related records.|Re-add the domain name.|

