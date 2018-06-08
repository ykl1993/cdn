# 设置HTTP头 {#concept_qxw_zkd_xdb .concept}

## 功能介绍 {#section_t35_fld_xdb .section}

可设置http响应头，目前提供9个http请求头参数可供自行定义取值，参数解释如下：

|参数|解释|
|:-|:-|
|Content-Type|指定客户程序响应对象的内容类型|
|Cache-Control|指定客户程序请求和响应遵循的缓存机制|
|Content-Disposition|指定客户程序响应对象时激活文件下载设置默认的文件名|
|Content-Language|指定客户程序响应对象的语言|
|Expires|指定客户程序响应对象的过期时间|
|Access-Control-Allow-Origin|指定允许的跨域请求的来源|
|Access-Control-Allow-Methods|指定允许的跨域请求方法|
|Access-Control-Max-Age|指定客户程序对特定资源的预取请求返回结果的缓存时间|
|Access-Control-Expose-Headers|指定允许访问的自定义头信息|

## 注意事项 {#section_lzt_fd2_xdb .section}

-   HTTP响应头的设置会影响该加速域名下所有资源的客户程序（例如浏览器）的响应行为，而不会影响缓存服务器的行为。
-   目前仅支持这些http头参数取值设置，有其他HTTP头部设置需求，请提工单反馈。
-   Access-Control-Allow-Origin参数的取值，支持`*`\(表示全部域名\)或者完整域名例如：`www.aliyun.com`；目前不支持泛域名设置。

## 配置引导 {#section_kv5_hd2_xdb .section}

1.  CDN域名概览页，选择域名进入域名配置页面，设置HTTP头。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3423_zh-CN.png)

2.  单击**修改配置**，可以管理当前http header的规则列表。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3424_zh-CN.png)

3.  单击**添加**，增加HTTP HEADER自定义设置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3425_zh-CN.png)


