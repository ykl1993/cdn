# Type 1: Images And Small Files Acceleration {#concept_jyb_1cf_xdb .concept}

## Use cases {#section_a4f_ydf_xdb .section}

Distribution of static website or application contents, such as various image files, HTML file, Flash animation, css and JavaScript files.  Suitable for portal websites, e-commerce websites, news websites and applications, government and enterprise official websites, and entertainment and game websites and applications.

## Procedure {#section_jnw_zdf_xdb .section}

1.  Add a CDN domain

    See [Quick Start](../intl.en-US/Quick Start/Quick Start.md#).Make sure you select **Acceleration of images and small files** for the business type.

2.  Configure domain

    After the domains are added, use the appropriate feature to configure the CDN domains based on your business needs. All domain configurations are optional. The following configurations are recommended for the acceleration of “ images and small files”.

    Recommended configurations:

    -   [HTTPS Secure Acceleration](intl.en-US//HTTPS Acceleration/HTTPS Security Acceleration.md#): You only need to enable the secure acceleration mode and then upload the certificate and the private key for the CDN domains. You can also view, disable or edit the certificate. For more information, see[证书格式说明](intl.en-US//HTTPS Acceleration/Certificate Format.md#)。
    -   [Cache configuration](intl.en-US/User Guide/Node Cache Settings/Cache policy configuration.md#), This feature can be used to set the actions of a cache server against resources in different **directory paths** or with different **file name suffixes**. You can customize cache expiration rules for specified resources.
    -   Access control settings: ensure the security of the distributed content, and prevent unnecessary traffic losses from leeching or malicious requests.
        -   [Refer anti-leech protection](intl.en-US/User Guide/Access Control Settings/Anti-leech.md#)
        -   [IP blacklist](intl.en-US/User Guide/Access Control Settings/IP blacklist.md#)
    -   Performance optimization settings: intelligently compress the distributed content and ignore URL parameters to improve cache hit rate.
        -   [Page optimization](intl.en-US/User Guide/Performance Optimization settings/Page optimization.md#)
        -   [Smart compression](intl.en-US/User Guide/Performance Optimization settings/Smart compression.md#)
        -   [Filter parameters](intl.en-US/User Guide/Performance Optimization settings/Filter parameter.md#)
    -   For more features, see [CDN feature list](intl.en-US/User Guide/Function overview.md#).

