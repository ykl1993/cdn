# Price overview {#concept_m3l_kvl_zdb .concept}

Alibaba Cloud CDN pricing system consists of basic services and value-added services.

## How to charge {#section_ost_zls_l2b .section}

-   Basic services: [PayByTraffic](intl.en-US/Pricing/Billing method/PayByTraffic.md#) and [PayByBandwidth](intl.en-US/Pricing/Billing method/PayByBandwidth.md#). You can switch between PayByTraffic and PayByBandwidth based on your needs. The new billing method will take effect for the billing cycle following the change. See the table below of different scenarios for the two billing methods.

    |Billing Method|Description| Scenarios|
    |:-------------|:----------|:---------|
    |PayByBandwidth| Users are billed by daily peak bandwidth. A peak bandwidth value is recorded at intervals of 5 minutes for a total of 288 values each day. The highest value is used for billing.|This billing method is best for scenarios where the domain name traffic curve is relatively flat or where bandwidth utilization exceeds 30% for the whole day.|
    |PayByTraffic|Users are billed according to the actual traffic used hourly.|This billing method is best for scenarios where the domain name traffic curve varies and bandwidth spikes, or where the bandwidth utilization is less than 30% for the whole day.|

    **Note:** Bandwidth utilization refers to actual used traffic \(Gbps\)/\(peak bandwidth \(Mbps\) x  10.54\). For 1 Mbps bandwidth, 100% utilization for a whole day would generate approximately 10.54 Gbps of traffic.

-   [Value-added services](intl.en-US/Pricing/Billing method/Value-added services.md#): when you have activated HTTPS Secure Acceleration service or Dynamic Route for CDN service, you shall pay the bill beyond basic service.

**Note:** [What's the differences between the traffic you billed and the traffic monitored by the console?](https://www.alibabacloud.com/help/faq-detail/40164.htm)

## How to pay {#section_mbr_rwl_l2b .section}

-   Post Payment: for all above-mentioned basic services or value-added services.
-   Prepayment: for [HTTPS requests](intl.en-US/Pricing/Billing method/Pre-paid HTTPS.md#).

## Pricing zones {#section_gl3_gdl_l2b .section}

Currently, Alibaba Cloud has 8 pricing zones: Mainland China \(CN\), North America  \(NA\), Europe \(EU\), Asia-Pacific 1 \(AP1\), Asia-Pacific 2 \(AP2\), Asia-Pacific 3 \(AP3\), Middle East and Africa \(MEAA\), and South America  \(SA\).

How pricing zones distributes:

-   Mainland China \(CN\):
-   Asia-Pacific 1 \(AP1\): Hong Kong, Taiwan, Macao, Japan and all Southeast Asia except Vietnam and Indonesia.
-   Asia-Pacific 2 \(AP2\): India, Indonesia, Korea, and Vietnam.
-   Asia-Pacific 3 \(AP3\): Australia and New Zealand.
-   North America \(NA\)
-   South America \(SA\)
-   Europe \(EU\)
-   Middle East & Africa \(MEAA\)

See the following table for the pricing details:

PayByBandwidth:

| Peak Bandwidth \(Unit: USD/Mbps/Day\)

 |Mainland China-CN|North America-NA|European Union-EU|Asia Pacific 1-AP1|Asia Pacific 2-AP2|Asia Pacific 3-AP3|Middle East & Africa-MEAA|South America-SA|
|-----------------------------------------|-----------------|----------------|-----------------|------------------|------------------|------------------|-------------------------|----------------|
|0Mbps ~ 500Mbps \(included\)|0.09|0.25|0.25|0.5|0.6|0.6|0.9|0.81|
|500Mbps ~ 5Gbps \(included\)|0.09|0.23|0.23|0.48|0.58|0.58|0.88|0.79|
|5Gbps ~ 20Gbps \(included\)|0.09|0.21|0.21|0.46|0.56|0.56|0.86|0.77|
|\>20Gbps|0.08|0.2|0.2|0.45|0.55|0.55|0.85|0.76|

PayByTraffic:

| Traffic \(Unit: USD/Mbps/Day\)

 |Mainland China-CN|North America-NA|European Union-EU|Asia Pacific 1-AP1|Asia Pacific 2-AP2|Asia Pacific 3-AP3|Middle East & Africa-MEAA|South America-SA|
|----------------------------------|-----------------|----------------|-----------------|------------------|------------------|------------------|-------------------------|----------------|
|0GB ~ 50TB \(included\)|0.04|0.07|0.07|0.12|0.12|0.13|0.2|0.2|
|50TB ~ 100TB \(included\)|0.03|0.06|0.06|0.1|0.11|0.11|0.18|0.18|
|100TB ~ 1PB \(included\)|0.03|0.03|0.03|0.08|0.1|0.095|0.15|0.14|
|\> 1PB|0.02|0.025|0.025|0.07|0.09|0.09|0.14|0.13|

