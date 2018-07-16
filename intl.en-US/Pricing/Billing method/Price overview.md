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

## How to pay {#section_mbr_rwl_l2b .section}

-   Post Payment: for all above-mentioned basic services or value-added services.
-   Prepayment: for [subscription traffic package](intl.en-US/Pricing/Billing method/Pre-paid traffic package.md#) or [HTTPS requests](intl.en-US/Pricing/Billing method/Pre-paid HTTPS.md#).

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

PayByBandwidth:![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15630/7130_en-US.png)

PayByTraffic:![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15631/7129_en-US.png)

## Other information {#section_nvx_wwl_zdb .section}

Metering data statistics

The system collects summary data from domain names of the nodes across the CDN at intervals of 5 minutes \(288 nodes a day\). This data is used as the basis for billing.

Differences between billed traffic and console monitoring traffic

The traffic shown on the console is derived from our log \(recorded at the application layer\) and is 7%-15% lower than the actual network traffic, due to:

-   Consumption by TCP/IP packet header: Our HTTP requests are based on TCP/IP. On the Internet, each packet contains up to 1,500 bytes, including a 40-byte header inserted by TCP/IP. This packet header also generates traffic. However, the packet header is added by the core protocol stack and cannot be counted by the application layer. Therefore, our log does not record these 40 bytes. This portion of traffic typically accounts for around 3% of the logged traffic.
-   TCP retransmission: Depending on the physical Internet load, about 3-10% of the packets we send are discarded by the Internet. The server will re-transmit such discarded packets over the core protocol stack, but the application layer is unable to count these packets. As a result, such traffic may make up a percentage of our logged traffic. The re-transmission rate may vary depending on the Internet connection quality. When Internet traffic is light, the re-transmission rate is low; during peak hours, the rate may rise 3%-7%.

Therefore, following industry standards, Alibaba Cloud includes an additional 7%-15% Internet traffic overhead in chargeable traffic. Alibaba Cloud takes the mean value of 10% and adds it to our statistics for Internet traffic consumption.

