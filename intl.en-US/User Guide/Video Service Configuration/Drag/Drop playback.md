# Drag/Drop playback {#concept_ptq_f1f_xdb .concept}

## Introduction {#section_oxh_h1f_xdb .section}

-   In a video on demand scenario, when the playback progress bar is dragged, the client will send a URL request similar to `http://www.aliyun.com/test.flv?start=10,` to the server. The server returns the data starting from the key frame bprior to the10th second to the client\( If start=10 is not the position of the key frame\).  
-   After receiving such a request from a client and the Drag/Drop Playback function is enabled, a CDN node can directly return the data starting from the key frame prior to the10th second \( If start=10 is not the position of the key frame\) \(FLV format\) or starting from the 10th second to the client.

## Attentions: {#section_hps_31f_xdb .section}

-   To use the Drag/Drop Playback function, an origin site must support Range requests. The origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.
-   The supported file formats are MP4 and FLV.
-   Currently, flv format only supports audio aac and video avc codeing formats, other encoding formats do not support drag and drop.

|File Format|Meta Information|start Parameter|Example|
|:----------|:---------------|:--------------|:------|
|MP4|Meta information of an origin site video must be contained in the file header. A video with its meta information contained in the file tail is not supported.|The start parameter specifies the time in seconds. Decimals are supported to indicate milliseconds. For example, start=1.01 indicates that the start time is 1.01s. If the current start is not a key frame, the CDN locates the key frame prior to the time specified by the start parameter.|The request http: //domain/video.mp4?start=10  playing a video from the 10th second.|
|FLV|An origin site video must contain meta information.|The start parameter specifies a byte. If the current start is not a key frame, the CDN automatically locates the key frame prior to the frame specified by the start parameter.|For http: //domain/video.flv, the request http:// domain/video.flv? start=10 playing a video from the key frame prior to the10th byte\( If start=10 is not the position of the key frame\) .|

## Procedure {#section_hxg_n1f_xdb .section}

-   This function is optional and is disabled by default.

-   Configuraton change

    In the CDN domain name management page, click **Configure**, Video related Enable/Disable**Drag/Drop Playback**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5156/3507_en-US.png)


