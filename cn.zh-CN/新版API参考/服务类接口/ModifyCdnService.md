# ModifyCdnService {#reference_llj_4bt_vdb .reference}

变更CDN服务的计费类型。

计费类型：

-   按峰值带宽计费
-   按使用流量计费

**说明：** 

-   需先开通才可执行此操作。
-   变更计费类型，次日00:00生效，多次变更以最新提交的为准。

## 请求参数 {#section_udw_bqn_cgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：ModifyCdnService。|
|InternetChargeType|String|是|开通服务的计费类型：按流量、按带宽峰值。用户必须指定类型：按流量“PayByTraffic”，按带宽峰值“PayByBandwidth”。|

## 示例 {#section_sz4_ctt_vdb .section}

请求示例

```
https://cdn.aliyuncs.com?&Action=ModifyCdnService&InternetChargeType=PayByTraffic&<公共请求参数>
```

返回示例

JSON格式：

```
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## 错误码 {#section_rr2_nqn_cgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|OperationDenied|Your account does not open CDN service yet.|403|您的账户未开通CDN服务。|
|InvalidParameter|The specified value of parameter parameter name is not valid.|400|参数parameter name无效。|
|InsufficientBalance|Your account does not have enough balance.|400|您的账户余额不足。|
|Forbidden.NotVerified|Your account is not verified yet.|403|您的账户未进行验证。|

