# OpenCdnService {#reference1159 .reference}

开通CDN服务。只有开通后，才能进行域名操作。

**说明：** 

-   一个用户只能开通一次。
-   开通条件：帐号已通过实名认证。

## 请求参数 {#section_qqcs .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：OpenCdnService。|
|InternetChargeType|String|是|开通服务的计费类型：按流量\(PayByTraffic\)、按带宽峰值\(PayByBandwidth\)。 如果您不指定，默认按流量（PayByTraffic）。|

## 示例 {#section_sl .section}

请求示例

```
https://cdn.aliyuncs.com?&Action=OpenCdnService&InternetChargeType=PayByBandwidth&<公共请求参数>
```

返回示例

JSON格式：

```
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## 错误码 {#section_n2j_ymn_cgb .section}

|错误代码|错误信息|HTTP状态码|描述|
|:---|:---|:------|:-|
|Forbidden.Intl|User not authorized to open Intl service.|403|您未被授权开通国际站服务。|
|InvalidInternetChargeType.ValueNotSupported|The specified value of parameter InternetChargeType is not valid.|400|参数InternetChargeType无效。|
|CdnService.HasOpened|Your CDN service has opened.|400|CDN服务已开通，请勿重复开通。|
|InsufficientBalance|Your account does not have enough balance.|400| 您的账户余额不足。如果您想继续使用CDN相关服务，请您及时进行[充值](https://expense.console.aliyun.com/)操作。

 |
|NoRealNameAuthentication|Real-name authentication is needed.|400|您需要进行[实名认证](https://account.console.aliyun.com/#/auth/home)。|

