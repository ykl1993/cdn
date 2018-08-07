# PayByBandwidth {#concept_a51_ggl_l2b .concept}

## Billing rules {#section_bcd_1wl_zdb .section}

-   Billing item: Peak bandwidth For more information, see [Pricing](https://www.alibabacloud.com/zh/product/cdn).
-   Payment method: Pay-As-You-Go
-   Billing rules: On a tiered pricing basis. The peak bandwidth is billed according to the specified unit price respectively.

    | Peak Bandwidth \(Unit: USD/Mbps/Day\)

 |Mainland China-CN|North America-NA|European Union-EU|Asia Pacific 1-AP1|Asia Pacific 2-AP2|Asia Pacific 3-AP3|Middle East & Africa-MEAA|South America-SA|
    |-----------------------------------------|-----------------|----------------|-----------------|------------------|------------------|------------------|-------------------------|----------------|
    |0Mbps ~ 500Mbps \(included\)|0.09|0.25|0.25|0.5|0.6|0.6|0.9|0.81|
    |500Mbps ~ 5Gbps \(included\)|0.09|0.23|0.23|0.48|0.58|0.58|0.88|0.79|
    |5Gbps ~ 20Gbps \(included\)|0.09|0.21|0.21|0.46|0.56|0.56|0.86|0.77|
    |\>20Gbps|0.08|0.2|0.2|0.45|0.55|0.55|0.85|0.76|

-   Billing cycle: Billed by day, and fees are deducted in real time \(the bill for the previous day is issued and the fees are deducted after 00:00 each day\).

**Note:** 

## Note {#section_ex1_2jl_l2b .section}

-   PayByBandwidth is based on the maximum bandwidth your CDN service on and overseas nodes has consumed \(in Mbps\) for the current day.
-   The billing time is the end of the current billing cycle \(on a calendar day basis \). A bill is usually issued within one hour after the current billing cycle ends. For example, the bill for June 17 is generated after 0:00 June 18. Fees are automatically deducted from your account balance.
-   PayByBandwidth is based on the maximum bandwidth your CDN service has consumed \(in Mbps\).
-   The default upper limit of bandwidth for PayByBandwidth is 100 Gbps.Open a ticket if you require more.

