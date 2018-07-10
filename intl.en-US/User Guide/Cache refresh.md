# Cache refresh {#concept_w2w_wd2_xdb .concept}

Log on to the CDN console, click **Refresh** to perform refresh operation.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5168/3428_en-US.png)

## URL refresh {#section_iyp_ff2_xdb .section}

Concept: Forces specified files on the CDN Cache node to expire in order to update back-to-source again.

Time to Take Effect: 5 to 10 minutes

Attentions:

-   Entered URL must contain `http://` or `https://`
-   Up to 2,000 URLs with the same ID can be refreshed and warmed up each day.
-   Provides an interface to refresh the cache in batches. For more information, see [RefreshObjectCaches](../../../../intl.en-US/API Reference/Refresh the preheating Interface/Cache refresh.md#).

## Directory refresh {#section_hv2_hf2_xdb .section}

Concept: Forces files in the specified directory on the CDN Cache node to expire in order to update back-to-source again. Can be used in scenarios with large amounts of content.

Time to Take Effect: 5 to 10 minutes

Attentions:

-   Up to 100 refresh requests can be submitted each day.
-   Entered content must begin with `http://` or `https://`, and end with `/`.
-   Provides an interface to refresh the cache in batches. For more information, see [RefreshObjectCaches](../../../../intl.en-US/API Reference/Refresh the preheating Interface/Cache refresh.md#).

## URL push {#section_zlc_3f2_xdb .section}

Concept: Actively pushes content from the origin site to the L2 Cache node. Upon first access, you can directly hit cache to relieve pressure on the origin site.

Time to Take Effect: 5 to 10 minutes

Attentions:

-   Entered URL must contain `http://` or `https://`
-   Up to 500 URLs with the same ID can be pushed each day.
-   Time to complete pushing resources depends on the number of pushed files submitted by the user, file size, origin site bandwidth, network condition and other factors.
-   Provides the interface to push resources in batches. For more information, see [PushObjectCache](../../../../intl.en-US/API Reference/Refresh the preheating Interface/PushObjectCache.md#).

## Progress view {#section_tlh_jf2_xdb .section}

-   You can log on to the CDN console **Refresh** \> **Operation Records**to view the progress of the resource refresh or push.
-   Alibaba Cloud CDN provides the API for querying progress: [DescribeRefreshTasks](../../../../intl.en-US/API Reference/Refresh the preheating Interface/DescribeRefreshTasks.md#).

