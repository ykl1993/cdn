# Price overview {#concept_m3l_kvl_zdb .concept}

The CDN price structure consists of basic services and value-added services.

-   Basic services:
    -   Two billing methods: PayByTraffic and PayByBandwidth. When activating the CDN service you must choose one of these methods.
    -   You can switch between PayByTraffic and PayByBandwidth based on your needs. The new billing method will take effect for the billing cycle following the change.
    -   See the following section for application scenarios of the two billing methods.

        |Billing Method|Description| Applicable Scenarios|
        |:-------------|:----------|:--------------------|
        |PayByBandwidth| Users are billed by daily peak bandwidth. A peak bandwidth value is recorded at intervals of 5 minutes for a total of 288 values each day. The highest value is used for billing.|This billing method is best for scenarios where the domain name traffic curve is relatively flat or where bandwidth utilization exceeds 30% for the whole day.|
        |PayByTraffic|Users are billed according to the actual traffic used hourly.|This billing method is best for scenarios where the domain name traffic curve varies and bandwidth spikes, or where the bandwidth utilization is less than 30% for the whole day.|

        **Note:** Bandwidth utilization refers to actual used traffic \(Gbps\)/\(peak bandwidth \(Mbps\) x  10.54\). For 1 Mbps bandwidth, 100% utilization for a whole day would generate approximately 10.54 Gbps of traffic.

-   Value-added services include:

    HTTPS Security acceleration service; when you open the HTTPS security acceleration sevice for a CDN domain name under your account, the domain name for which security acceleration service is activated and the basic services are also charged for the number of HTTPS requests.


## PayByBandwidth {#section_bcd_1wl_zdb .section}

-   Billing item: Peak bandwidth
-   For more information, see[Price details](https://www.alibabacloud.com/product/cdn?spm=a3c0i.7911826.675768.dnavproductsb3.8b024c7s89m5C#pricing).

    **Note:** 

    -   PayByBandwidth is based on the maximum bandwidth your CDN service on and overseas nodes has consumed \(in Mbps\) for the current day.
    -   The billing time is the end of the current billing cycle \(on a calendar day basis \). A bill is usually issued within one hour of the end of the current billing cycle. For example, the bill for June 17 will be generated after 0:00 June 18.  The amount due is automatically deducted from your account balance.
    -   PayByBandwidth is based on the maximum bandwidth your CDN service has consumed \(in Mbps\).
    -   The default upper limit of bandwidth for PayByBandwidth is 100 Gbps. Submit a ticket if you require a higher limit.

## PayByTraffic {#section_of4_fwl_zdb .section}

-   Billing item: Downstream traffic
-   For more information, see[Price details](https://www.alibabacloud.com/product/cdn?spm=a3c0i.7911826.675768.dnavproductsb3.8b024c7s89m5C#pricing).
-   Billing rules

    1.  Billing item: Traffic
    2.  Method of payment: Post payment
    3.  Billing rules: Pay by traffic on a tiered pricing basis and carry forward the amount of traffic exceeding the limit for the current month to the next billing cycle \(on a calendar month basis\).
    4.  Billing cycle: Billed by the hour; fee deducted in real time
    **Note:** 

    -   To avoid high costs due to irregular and/or malicious traffic, set the upper bandwidth limit for PayByTraffic to 10 Gbps by default.
    -   The billing time ends with the current billing cycle. A bill is typically issued within one hour of the end of the current billing cycle. For example, the bill for traffic consumed between 10:00-11:00 will be generated after 11:00. The amount due is then automatically deducted from your account balance.
    -   In the following conditions, you are still charged even you have purchased traffic package:
        -   Your usage has been over the limit of traffic package.
        -   You have purchaged the traffic package, without other value-added services, such as HTTPS request packages.
        -   You have used the traffic beyond mainland China.
        -   You have choosed the billing method as PayByBandwidth.

## Value-added services: {#section_jdt_lwl_zdb .section}

Number of HTTPS requests

-   For more information, see [Price details](https://www.alibabacloud.com/**%E6%B3%A8%EF%BC%9A**%20%20%E4%B8%BA%E9%98%B2%E6%AD%A2%E5%BC%82%E5%B8%B8%E7%9A%84%E6%81%B6%E6%84%8F%E6%B5%81%E9%87%8F%E7%BB%99%E7%94%A8%E6%88%B7%E9%80%A0%E6%88%90%E6%8D%9F%E5%A4%B1%EF%BC%8C%E6%8C%89%E6%B5%81%E9%87%8F%E4%BB%98%E8%B4%B9%E6%96%B9%E5%BC%8F%EF%BC%8C%E9%BB%98%E8%AE%A4%E5%B8%A6%E5%AE%BD%E4%B8%8A%E9%99%90%E4%B8%BA10Gbps).
-   Billing rules

    1.  Billing item: HTTPS requests
    2.  Method of payment: Post payment
    3.  Billing rule: Billing is based on the HTTPS request price for value-added services. HTTPS requests are accumulated on a calendar day basis.
    4.  Billing cycle: Billed by the day; fee deducted in real time \(The bill for the previous day is issued and the fee deducted after 00:00 each day.\)
    **Note:** 

    -   The billing time is the end of the current billing cycle \(on a calendar day basis \). A bill is typically issued within one hour of the end of the current billing cycle. For example, the bill for June 17 will be generated after 0:00 June 18. The amount due is then automatically deducted from your account balance.
    -   Billing of HTTPS requests: Settlement is based on the cumulative HTTPS requests generated by all domains for which secure acceleration is activated on the current day.

## Pre-paid traffic package {#section_o1z_pwl_zdb .section}

-   Traffic package sizes from**500G ~ 50TB** are available for 1 year. Learn more. Fore more information, see [learn more](https://common-buy.aliyun.com/?commodityCode=cdnflowbag_intl#/buy)。
-   The packages are pre-paid in Subscription mode \(paid in one total sum and activated immediately\). The traffic beyond the package quota is billed in Pay-As-You-Go mode.
-   For the duration of the resource package, fees are deducted for your use of the traffic quota. For traffic outside the quota, fees are billed based on the existing billing rules.

-   Billing rules

    1.  Billing items: domestic traffic+international traffic
    2.  Method of payment: Prepayment
    3.  Billing cycle: Billed by the hour and charged in real time \(a bill is generated every hour and the used traffic is deducted from the traffic package\).
-   Notice for use:

    1.  You can buy a pre-paid traffic package with a credit card.
    2.  Traffic packages only support the Pay-As-You-Go billing mode. If the billing mode of your traffic package is PayByBandwidth, the balance of your traffic package will be frozen until you switch to Pay-As-You-Go.
    3.  CDN traffic packages \(global\) allow you to deduct the traffic generated by domestic and international nodes.
    4.  Traffic packages are limited to your own account only.
    5.  Traffic packages are prioritized and used based on expiration time. Traffic is deducted first from the traffic package that will expire soonest.
    6.  To view the balance of your traffic package, go to **User center** \> **Cost center** \> ****[Resource Package Management.](http://expense.console.aliyun.com/#/flow/home) .
    7.  Your traffic package is only valid during the specified validity period. Any unused traffic will expire when the traffic package expires, and Alibaba Cloud will not provide replacements or complements.

## Other information {#section_nvx_wwl_zdb .section}

The system collects summary data from domain names of the nodes across the CDN at intervals of 5 minutes \(288 nodes a day\). This data is used as the basis for billing.

The traffic shown on the console is derived from our log \(recorded at the application layer\) and is 7%-15% lower than the actual network traffic, due to:

-   Consumption by TCP/IP packet header: Our HTTP requests are based on TCP/IP. On the Internet, each packet contains up to 1,500 bytes, including a 40-byte header inserted by TCP/IP. This packet header also generates traffic. However, the packet header is added by the core protocol stack and cannot be counted by the application layer. Therefore, our log does not record these 40 bytes. This portion of traffic typically accounts for around 3% of the logged traffic.
-   TCP retransmission: Depending on the physical Internet load, about 3-10% of the packets we send are discarded by the Internet. The server will re-transmit such discarded packets over the core protocol stack, but the application layer is unable to count these packets. As a result, such traffic may make up a percentage of our logged traffic. The re-transmission rate may vary depending on the Internet connection quality. When Internet traffic is light, the re-transmission rate is low; during peak hours, the rate may rise 3%-7%.

Therefore, following industry standards, Alibaba Cloud includes an additional 7%-15% Internet traffic overhead in chargeable traffic. Alibaba Cloud takes the mean value of 10% and adds it to our statistics for Internet traffic consumption.

