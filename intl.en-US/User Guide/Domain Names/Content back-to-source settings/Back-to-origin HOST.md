# Back-to-origin HOST {#concept_epk_z1d_xdb .concept}

## Introduction {#section_qtb_dbd_xdb .section}

With this function, you can specify the domain name that the system need to access during CDN back-to-source. You can choose the domain type of acceleration domain, origin domain, or custom domain.

**Note:** Specify the domain name if your origin site has been bound to multiple sites or domain names. Otherwise, your back-to-source will fail.

-   By default, the Back-to-origin HOST is set as the following:
    -   If the source site is of IP type, the return source host will by default accelerate the domain name.
    -   If the source site is OSS source type, the source host is the source domain name by default.
-   The options are: accelerating domain names, source site domain names, and custom domain names.

**Note:** SNI back-to-origin is unavailable currently.

## Configuration {#section_tk3_dbd_xdb .section}

Change configuration: Enter CDN domain name management page, select domain name access configuration page, return to source settings, you can modify the configuration of the returned host.

![](images/3347_en-US.png)

The difference between a source station and a return source host \(one IP/host is capable of binding Multiple Domain Names/sites\) ,, therefore, you need to specify which domain name/site to return to when the source is returned by setting the feed host \):

-   Source station: the source station determines which IP to request when the source is returned.
-   Back to source host: The back to source host determines which site on the IP to access from Back To The Source request. \( If you have an IP source station bound, you need to set up multiple domain names/sites The returned source host specifies which domain name the returned source is to, or the returned source fails \).

**Note:** 

-   Example 1: The source station is the domain name source for www.a.com the return source host is set to www. B .com, So the actual return source is M. Www.a.com resolve to the IP corresponding to the specific site: www. B .com.
-   Example 2: source station is IP source station 1. 1. 1. 1 The return source host is set to www. B .com, and the actual return source is the specific site that corresponds to 1. 1. 1. 1: www. B .com.

