# Peak Bandwidth {#concept_tlh_bh2_xdb .concept}

## Introduction {#section_uws_ch2_xdb .section}

The bandwidth cap function sets the maximum bandwidth value for average bandwidth measured during each statistical cycle \(five minutes\). If the average bandwidth exceeds the maximum, the domain name automatically goes offline to protect your domain name security. In this situation, all requests are sent back to the origin site. When the bandwidth cap is reached, CDN stops acceleration services to avoid excessive fees produced by abnormal traffic volumes. After your domain name goes offline, you can restart it in the console.

**Note:** The bandwidth cap function is not currently available for wildcard domain names, so the function has no effect even it is enabled.

RAM subaccounts require CloudMonitor authorization to use this function. To grant authorization, use the **AliyunCloudMonitorFullAccess** policy group.

## Procedure {#section_twz_gh2_xdb .section}

**Note:** After you have enabled the peak bandwidth function, your services are limited by the bandwidth cap and go offline if it is exceeded. To guarantee your services running continuously on your domain name, we recommend you set the cap value with discretion based on reasonable estimation.

1.  Log on to the CDN console.
2.  On the Domain Names page, choose the domain name, then click **Manage**.
3.  Choose **Advanced Settings**, then click **Modify** under the **Peak Bandwidth** label.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5175/154261193632303_en-US.png)
4.  Enable the bandwidth cap function. Choose the unit from Mbps, Gbps, or Tbps.

    **Note:** Bandwidth value can be set in powers of thousand.

5.  Click **Confirm**. Then the peak bandwidth is successfully enabled.

You can choose to enable or disable the peak bandwidth function based on the actual usage of your domain name.

