# Resource monitoring {#concept_ajm_xq2_xdb .concept}

Monitoring page functions:

-   Resource monitoring provides Resource Usage, Statistics Analysis, Ranking by Access and Hot Spot Analysis.
-   You export original data of Traffic bandwidth, Access overview,  Ranking by Access rate, Visitor data,  and operators distribution and other deatils.
-   A difference exists between the graph data and the billing data in Resource Monitoring. For example, a 30-day statistical curve takes a granularity of 14400s and a billing data granularity of 300s, so the graph ignores some metering points and is mainly used as a description of bandwidth trends. Bandwidth usage is subject to precise granularity of billing data.

**Note:** The precision of original data collection varies according to time spans, which are 300s, 3600s, and 14400s for daily export, weekly export, and monthly export, respectively .

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5169/3475_en-US.png)

|Item|Metric|Time Span|
|:---|:-----|:--------|
|Resource Usage|Network traffic, domain name ranking, back-to-source traffic, daily traffic statistics|Today, yesterday, within 7 days, 30 days, and user-defined 90 days|
|Statistical analysis|PV, UV, regional user distribution, operator proportions|Today, yesterday, within 7 days, 30 days, and user-defined 90 days|
|Domain name ranking|Access rankings for each CDN domain name|Today, yesterday, within 7 days, 30 days, and user-defined 90 days|
|Hot spot analysis|File response ratio, URL access statistics, page reference URL ratio|Support viewing one-day data, user-defined 90 days|

