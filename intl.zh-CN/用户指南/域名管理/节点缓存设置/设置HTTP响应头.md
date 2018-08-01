# 设置HTTP响应头 {#concept_qxw_zkd_xdb .concept}

## 功能介绍 {#section_t35_fld_xdb .section}

HTTP消息头是指，在超文本传输协议（ Hypertext Transfer Protocol ，HTTP）的请求和响应消息中，协议头部的组件。HTTP消息头准确描述了正在获取的资源、服务器或客户端的行为，定义了HTTP事务中的具体操作参数。

在HTTP消息头中，按其出现的上下文环境，分为通用头、请求头、响应头等。其中，HTTP响应头为响应消息提供了更多信息，允许服务器传递不能放在状态行的附加信息，通常用来描述服务器的信息和 Request-URI进一步的信息。

目前阿里云提供9个HTTP响应头参数可供您自行定义取值，参数解释如下：

|参数|描述|
|:-|:-|
|Content-Type|指定客户端程序响应对象的内容类型。|
|Cache-Control|指定客户端程序请求和响应遵循的缓存机制。|
|Content-Disposition|指定客户端程序把请求所得的内容存为一个文件时提供的默认的文件名。|
|Content-Language|指定客户端程序响应对象的语言。|
|Expires|指定客户端程序响应对象的过期时间。|
|Access-Control-Allow-Origin|指定允许的跨域请求的来源。|
|Access-Control-Allow-Methods|指定允许的跨域请求方法。|
|Access-Control-Max-Age|指定客户端程序对特定资源的预取请求返回结果的缓存时间。|
|Access-Control-Expose-Headers|指定允许访问的自定义头信息。|

**说明：** 请求对象分为请求头、请求行以及请求实体；响应对象分为响应行、响应头和响应实体。

## 注意事项 {#section_lzt_fd2_xdb .section}

-   HTTP响应头的设置会影响该加速域名下所有资源客户端程序（例如浏览器）的响应行为，但不会影响缓存服务器的行为。
-   目前仅支持上述HTTP头参数取值设置。如果您有其他HTTP头部设置需求，请[提交工单](https://workorder-intl.console.aliyun.com)反馈。
-   关于参数Access-Control-Allow-Origin的取值，您可以填写`*`表示全部域名；也可以填写完整域名，例如：`www.aliyun.com`。
-   目前不支持泛域名设置。

## 操作步骤 {#section_kv5_hd2_xdb .section}

1.  登录CDN控制台，进入域名管理页面，选择需要设置的域名，单击**管理**。
2.  在**缓存配置** \> **HTTP头**，您可以单击**修改**或**删除**对HTTP的参数进行相应操作。
3.  您也可以单击**添加**，选择参数，并输入取值，然后单击**确认**，添加自定义HTTP头参数。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/15330914197278_zh-CN.png)

