# Scenarios {#concept_o5j_x3g_tdb .concept}

## To accelerate the distribution of resources for websites, or applications, {#section_smn_pjg_tdb .section}

with a large volume of static resources. We recommend that you separate the dynamic and static contents. You can use Alibaba Cloud CDN to accelerate the static content, and use [Dynamic Route for CDN](https://www.alibabacloud.com/help/doc-detail/65098.htm) to accelerate dynamic content. For large volumes of static resources such as image, css, and small js files, we recommend that you store them on OSS. This can accelerate content download speeds and make it easy to perform distribution for images, videos, and other media content.

Architecture

## Acceleration of on-demand audio and video/large file downloads and distribution {#section_umn_pjg_tdb .section}

Alibaba Cloud CDN supports the downloading and distributing of various types of files. It also supports the acceleration of online on-demand streaming services, for example, MP4 and FLV videos, or scenarios where the average size of a single file is greater than 20 MB. The primary service scenarios are on-demand video/audio and large file downloads \(for example, installation packages\). You can combine CDN with OSS to increase origin retrieval speeds to reduce origin retrieval bandwidth cost by 2/3.

Architecture

 

## Live acceleration {#section_wmn_pjg_tdb .section}

Architecture

 

## Mobile application acceleration {#section_ymn_pjg_tdb .section}

For the distribution of mobile app update files \(APK files\), CDN delivers optimized and accelerated distribution of in-app images, pages, short videos, UGC, and other media content. The http DNS service prevents DNS hijacking and retrieves precise DNS resolution results in real time, effectively reducing user access time and improving user experience.

Architecture

