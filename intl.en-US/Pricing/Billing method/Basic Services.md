# Basic Services {#concept_a51_ggl_l2b .concept}

For basic services, you can choose any of two methods for billing: PayByBandwidth or PayByTraffic.

See the [Pricing Details](https://www.alibabacloud.com/product/cdn/pricing) in different zones.

Choose the billing method suitable for you according to the table below.

|When your ...|We recommend ...|Description|
|-------------|:---------------|:----------|
|Domain name traffic curve is relatively flat or bandwidth utilization exceeds 30% for the whole day.|[PayByBandwidth](intl.en-US/Pricing/Billing method/Basic Services.md#section_bcd_1wl_zdb)| You are billed by daily peak bandwidth. A peak bandwidth value is recorded at intervals of 5 minutes for a total of 288 values each day. The highest value is used for billing.|
|Domain name traffic curve varies and bandwidth spikes, or where the bandwidth utilization is less than 30% for the whole day.|[PayByTraffic](intl.en-US/Pricing/Billing method/Basic Services.md#section_ejq_v5h_t2b)|Your are billed according to the actual traffic used hourly.|

## PayByBandwidth {#section_bcd_1wl_zdb .section}

-   Billing item: Peak bandwidth.
-   Payment method: Pay-As-You-Go.
-   Billing cycle: Billed by day, and fees are deducted in real time \(the bill for the previous day is issued and the fees are deducted after 00:00 each day\).
-   Billing standard: PayByBandwidth is based on the maximum bandwidth your CDN service on and overseas nodes has consumed \(in Mbps\) for the current day. The default limit of upper bandwidth for PayByBandwidth is 100 Gbps. Submit a ticket if you have other requirements.
-   On a tiered pricing basis. The peak bandwidth is billed according to the specified unit price respectively.

    Billing time: the end of the current billing cycle \(on a calendar day basis \). A bill is usually issued within one hour after the current billing cycle ends. For example, the bill for June 17 is generated after 0:00 June 18. Fees are automatically deducted from your account balance.


## PayByTraffic {#section_uhd_fwp_w2b .section}

-   Billing item: Downstream traffic.
-   Payment method: Pay-As-You-Go.
-   Upper bandwidth limit by default: 10Gbps. \(Reason: to avoid high costs due to irregular or malicious traffic\)
-   Billing cycle: Billed by hour, and the fees are deducted in real time.
-   How to calculate traffic data: The system collects summary data from domain names of the nodes across the CDN at intervals of 5 minutes \(288 nodes a day\). This data is used as the basis for billing. [What's the differences between the traffic you billed and the traffic monitored by the console?](https://www.alibabacloud.com/help/faq-detail/40164.htm)
-   Billing rules: Pay by traffic on a tiered pricing basis according to different billing zones monthly.

-   Billing standard: the billing time ends with the current billing cycle. A bill is typically issued within one hour after the current billing cycle ends. For example, the bill for traffic consumed between 10:00-11:00 is generated after 11:00. Fees are then automatically deducted from your account balance.


**Note:** In the following conditions, you are still charged even you have bought traffic package:

-   You have used up the amount of the traffic package.
-   You have bought the traffic package only, without other value-added services, such as HTTPS request packages.
-   You have used the traffic when you are outside mainland China.
-   You have selected the billing method as **PayByBandwidth**.

