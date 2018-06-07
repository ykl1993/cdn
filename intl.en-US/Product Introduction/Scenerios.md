# Scenerios {#concept_o5j_x3g_tdb .concept}

## Website/application acceleration {#section_smn_pjg_tdb .section}

To accelerate the distribution of resources for websites, or applications, with a large volume of static resources, you can separate the dynamic and static contents.  The dynamic files can be stored on ECS. For large volumes of static resources such as image, HTML, CSS, and JS files, we recommend that you store them on OSS.  This can accelerate content download speeds and make it easy to  perform distribution for images, videos,  and other media content.

Architecture

## Acceleration of on-demand audio and video/large file downloads and distribution {#section_umn_pjg_tdb .section}

Alibaba Cloud CDN supports the downloading and distributing of various types of files. It also supports the acceleration of online on-demand streaming services, for example, MP4 and FLV videos, or scenarios where the average size of a single file is greater than 20 MB. The primary service scenarios are on-demand video/audio and large file downloads \(for example, installation packages\). You can combine CDN with OSS to increase origin retrieval speeds to reduce origin retrieval bandwidth cost by nearly 60%.

Architecture

 

## Live acceleration {#section_wmn_pjg_tdb .section}

Alibaba cloud [Live streaming](https://www.alibabacloud.com/zh/product/apsaravideo-for-live?spm=a2796.7919406.1097650.dznavproductsj1.62616ecf7Cjj4c) The service has been released on-line separately. The live streaming media service provides an integrated solution for media asset storage, slicing and transcoding, access authentication, and content delivery acceleration.  Combined with Alibaba Cloud Auto Scaling, CDN can promptly adjust server bandwidth and respond to sudden access traffic bursts. When combined with the media transcoding service, CDN can provide high-speed and stable concurrent transcoding and seamless task scaling.

Architecture

 

## Mobile application acceleration {#section_ymn_pjg_tdb .section}

For the distribution of mobile app update files \(APK files\), CDN delivers optimized and accelerated distribution of in-app images, pages, short videos, UGC, and other media content.  The http DNS service prevents DNS hijacking and retrieves precise DNS resolution results in real time, effectively reducing user access time and improving user experience. Download PDF

Architecture

## Other CDN Products {#section_vpw_1lg_tdb .section}

-   For higher security requirements for CDN acceleration, use [SCDN](https://help.aliyun.com/product/63560.html).
-   To further reduce CDN costs with P2P technology, use [PCDN](https://help.aliyun.com/product/54287.html).
-   For specific demand of dynamic contents, use [Dynamic Route for CDN](https://help.aliyun.com/document_detail/62975.html)

