# PayByTraffic {#concept_hll_khl_l2b .concept}

## Billing rules {#section_of4_fwl_zdb .section}

-   Billing item: Downstream traffic For more information, see [Pricing](https://www.alibabacloud.com/zh/product/cdn).
-   Payment method: Pay-As-You-Go
-   Billing rules: Pay by traffic on a tiered pricing basis and carry forward the amount of traffic exceeding the limit for the current month to the next billing cycle \(on a calendar month basis\).![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15631/7129_en-US.png)
-   Billing cycle: Billed by hour, and the fees are deducted in real time.
-   How to calculate traffic data: The system collects summary data from domain names of the nodes across the CDN at intervals of 5 minutes \(288 nodes a day\). This data is used as the basis for billing. [What's the differences between the traffic you billed and the traffic monitored by the console?](https://www.alibabacloud.com/help/faq-detail/40164.htm)

## Note {#section_sgb_zhl_l2b .section}

-   To avoid high costs due to irregular and/or malicious traffic, the upper bandwidth limit for PayByTraffic is set to 10 Gbps by default.
-   The billing time ends with the current billing cycle. A bill is typically issued within one hour after the current billing cycle ends. For example, the bill for traffic consumed between 10:00-11:00 is generated after 11:00. Fees are then automatically deducted from your account balance.
-   In the following conditions, you are still charged even you have bought traffic package:
    -   You have used up the quota of the traffic package.
    -   You have bought the traffic package only, without other value-added services, such as HTTPS request packages.
    -   You have used the traffic when you are outside mainland China.
    -   You have selected the billing method as **PayByBandwidth**.

