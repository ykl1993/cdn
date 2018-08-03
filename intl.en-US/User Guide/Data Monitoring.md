# Data Monitoring {#concept_xgl_mk4_m2b .concept}

Data Monitoring includes Resource Monitoring and Real-time Monitoring.

## Resource Monitoring {#section_cfb_jm4_m2b .section}

You can select **Domain Name**, **Region**, **Operator**, **Time Granularity** \(**1 minute**, **5 minute** or **1 hour**\) and **Time Range** \(**Today**, **Yesterday**, **7 Days**, **30 Days** or **Custom**\) to view the specific condition in the following dimensions:

|Items|Metrics|
|:----|:------|
|Traffic Bandwidth|Bandwidth, Traffic|
|Back-to-origin Statistics|Back-to-origin Bandwidth, Back-to-origin Traffic|
|Number of Visits|Number of requests, QPS.|
|HTTPS Hit Rate|N/A|
|HTTPCODE|5xx, 4xx, 3xx, 2xx|

A difference exists between the graph data and the billing data in Resource Monitoring. For example, a 30-day statistical curve takes a granularity of 14400s, while the billing statistical curve takes a granularity of 300s. As a result, the graph, ignoring some metering points, is mainly used to show the trends of bandwidth. The billing data, with more precise granularity, always serves as the basis to calculate your bandwidth usage.

**Note:** HTTP Hit Rate is not available for selecting Region or Operator.

## Real-time Monitoring {#section_g5p_lm4_m2b .section}

You can select the**Domain Name**, **Region**, **Operator** or the **Time Range** you want to view \(**Past 1 Hour**, **Past 6 hours**, **Past 12 hours** or **Custom**\) to view the specific condition in the following dimensions:

|Items|Metrics|
|:----|:------|
|Basic Data|Bandwidth, Traffic, Number of requests, QPS|
|Back-to-origin Traffic|Back-to-origin Traffic, Back-to-origin Bandwidth|
|Quality monitoring|Request Hit Rate, Byte Hit Rate, 5xx status code, 4xx status code, 3xx status code, 2xx status code.|

## Procedure {#section_kv5_hd2_xdb .section}

1.  Log on to the CDN console, then go to the Domain Names page. Choose a domain name, then click **Manage**.
2.  Go to **Data Monitoring** \> **Resource Monitoring** or **Real-time Monitoring**, and select the monitoring items and metrics. Click **Query**.

    **Resource Monitoring**：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15915/15332798268908_en-US.png)

    **Real-time Monitoring**：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15915/15332798268909_en-US.png)


