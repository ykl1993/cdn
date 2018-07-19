# Drag/Drop Playback {#concept_ptq_f1f_xdb .concept}

## Introduction {#section_oxh_h1f_xdb .section}

In a video-on-demand scenario, when the playback progress bar is dragged, the end user will send a URL request, such as `http://www.aliyun.com/test.flv?start=10`, to the server. The server returns the data from the key frame prior to the10th second to the client \(If start=10 is not the key frame\).  

After receiving such a request from an end user and the Drag/Drop Playback function is enabled, a CDN node can directly return the data from the key frame prior to the10th second \(If start=10 is not the key frame\) \(FLV format\) or from the 10th second to the end user.

## Note {#section_hps_31f_xdb .section}

-   To use the Drag/Drop Playback function, an origin site must support Range requests. The origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.
-   Two available file format: MP4 and FLV.
-   Currently, FLV format only supports the coding formats with the audio format of aac and video format of avc.

|File Format|Meta Information|start Parameter|Example|
|:----------|:---------------|:--------------|:------|
|MP4|Meta information of an origin site video must be contained in the file header. A video with its meta information contained in the file tail is not supported.|The start parameter specifies the time in seconds. Decimals are supported to indicate milliseconds. For example, start=1.01 indicates that the start time is 1.01s. If the current start is not a key frame, the CDN locates the key frame prior to the time specified by the start parameter.|The request http: //domain/video.mp4?start=10  playing a video from the 10th second.|
|FLV|An origin site video must contain meta information.|The start parameter specifies a byte. If the current start is not a key frame, the CDN automatically locates the key frame prior to the frame specified by the start parameter.|For http: //domain/video.flv, the request http:// domain/video.flv? start=10 playing a video from the key frame prior to the10th byte\( If start=10 is not the position of the key frame\) .|

## Procedure {#section_hxg_n1f_xdb .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  Enable the function in **Video-related** \> **Drag/Drop Playback**.

