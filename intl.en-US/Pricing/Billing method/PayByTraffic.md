# PayByTraffic {#concept_hll_khl_l2b .concept}

## Billing details {#section_of4_fwl_zdb .section}

-   Billing item: Downstream traffic. For more information, see [Pricing](https://www.alibabacloud.com/zh/product/cdn).
-   Payment method: Pay-As-You-Go.
-   Upper bandwidth limit by default: 10Gbps. \(Reason: to avoid high costs due to irregular or malicious traffic\)
-   Billing cycle: Billed by hour, and the fees are deducted in real time.
-   How to calculate traffic data: The system collects summary data from domain names of the nodes across the CDN at intervals of 5 minutes \(288 nodes a day\). This data is used as the basis for billing. [What's the differences between the traffic you billed and the traffic monitored by the console?](https://www.alibabacloud.com/help/faq-detail/40164.htm)

## Billing rules {#section_sgb_zhl_l2b .section}

Billing rules: Pay by traffic on a tiered pricing basis according to different billing zones monthly.

| Traffic \(Unit: USD/Mbps/Day\)

 |Mainland China-CN|North America-NA|European Union-EU|Asia Pacific 1-AP1|Asia Pacific 2-AP2|Asia Pacific 3-AP3|Middle East & Africa-MEAA|South America-SA|
|----------------------------------|-----------------|----------------|-----------------|------------------|------------------|------------------|-------------------------|----------------|
|0GB ~ 50TB \(included\)|0.04|0.07|0.07|0.12|0.12|0.13|0.2|0.2|
|50TB ~ 100TB \(included\)|0.03|0.06|0.06|0.1|0.11|0.11|0.18|0.18|
|100TB ~ 1PB \(included\)|0.03|0.03|0.03|0.08|0.1|0.095|0.15|0.14|
|\> 1PB|0.02|0.025|0.025|0.07|0.09|0.09|0.14|0.13|

Billing standard: the billing time ends with the current billing cycle. A bill is typically issued within one hour after the current billing cycle ends. For example, the bill for traffic consumed between 10:00-11:00 is generated after 11:00. Fees are then automatically deducted from your account balance.

**Note:** In the following conditions, you are still charged even you have bought traffic package:

-   You have used up the amount of the traffic package.
-   You have bought the traffic package only, without other value-added services, such as HTTPS request packages.
-   You have used the traffic when you are outside mainland China.
-   You have selected the billing method as **PayByBandwidth**.

