# Configuration change procedure {#concept_frf_pkv_tdb .concept}

## Change change instructions {#section_cw3_nnv_tdb .section}

1.  The current billing method is indicated on the CDN console overview page. If you need to change your billing type, click **Change billing method**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27273/cn_zh/1498549019223/DingTalk20170627153546.png)

    **Note:** Note: If you buy a package, choose PayByTraffic as your billing method.

2.  On the Enable Service page, you can see your current billing type, the following is the new billing method which it will be changed to.  that is about to change, click activate.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5109/5061_en-US.png)

3.  The system will change the configuration at 00:00 on the second calendar day after the end of the current billing cycle. It takes 1 to 10 minutes to change the configuration.   You may not submit another configuration change request for this CDN instance until the current configuration change takes effect.

    -   A change from a PayByTraffic to PayByBandwidth billing type will take effect at 00:00 on the second day.
    -   A change from a PayByBandwidth to PayByTraffic billing type will take effect at 00:00 on the second day.
    -   A change from a PayByTraffic or PayByBandwidth to Pay by 95 Monthly Bandwidth billing type will take effect at 00:00 on the second day.
    -   A change from Pay by 95 Monthly Bandwidth to PayByTraffic or PayByBandwidth billing type will take effect at 00:00 on the next natural month, and changes are not permitted in the month.
    **Note:** If you mis-change the configuration, you cannot re-change until 00:00 on the second day.  


