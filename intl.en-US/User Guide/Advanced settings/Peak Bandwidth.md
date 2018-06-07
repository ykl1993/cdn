# Peak Bandwidth {#concept_tlh_bh2_xdb .concept}

## Introduction {#section_uws_ch2_xdb .section}

The bandwidth cap function sets the maximum bandwidth value for average bandwidth measured during each statistical cycle \(five minutes\).If the average bandwidth exceeds the maximum, the domain name automatically goes offline to protect your domain name security. In this situation, all requests are sent back to the origin site.  When the bandwidth cap is reached, CDN stops acceleration services to avoid excessive fees produced by abnormal traffic volumes.  After your domain name goes offline, you can restart it in the console.

**Note:** The bandwidth cap function is not currently available for wildcard domain names, so the function has no effect even it is enabled.

RAM subaccounts require CloudMonitor authorization to use this function. To grant authorization, use the**AliyunCloudMonitorFullAccess**policy group.

## How do I enable the bandwidth cap function? {#section_twz_gh2_xdb .section}

1.  Click**Configure**in Domain Names page, go to **Security Settings**on the configuration page of the selected domain name, and click**Modify Configuration**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5175/3434_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5175/3435_en-US.png)

2.  Enable the bandwidth cap function. The bandwidth is measured in Mbps, Gbps, or Tbps.

    **Note:** bandwidth value can be set in powers of thousand

3.  The bandwidth cap function is successfully enabled.

    ![](images/3436_en-US.png)

4.  You can choose to enable or disable the bandwidth cap function based on the actual usage of your domain name.

## Attentions: {#section_crn_5h2_xdb .section}

After you enable the bandwidth cap function, your services are limited by the bandwidth cap and go offline if it is exceeded. To avoid affecting the services on your domain name, we recommend you set the cap value with discretion based on reasonable estimation.

