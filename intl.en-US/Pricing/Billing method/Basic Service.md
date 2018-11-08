# Basic Service {#concept_m3l_kvl_zdb .concept}

Alibaba Cloud CDN billing methods charges for two parts of services: basic services and value-added services.

## Billing Methods {#section_ost_zls_l2b .section}

|When your ...|We recommend ...|Description|
|-------------|:---------------|:----------|
|Domain name traffic curve is relatively flat or bandwidth utilization exceeds 30% for the whole day.|PayByBandwidth| You are billed by daily peak bandwidth. A peak bandwidth value is recorded at intervals of 5 minutes for a total of 288 values each day. The highest value is used for billing.|
|Domain name traffic curve varies and bandwidth spikes, or where the bandwidth utilization is less than 30% for the whole day.|PayByTraffic|Your are billed according to the actual traffic used hourly.|

**Note:** The traffic shown on the console is derived from our log recorded at the application layer, which is 7%-15% lower than the actual network traffic. For more information, see

