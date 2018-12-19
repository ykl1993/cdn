# DescribeCdnUserQuota {#reference1109 .reference}

查询用户资源上限及已使用情况。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeCdnUserQuota。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|DomainQuota|Integer|加速域名数上限。|
|RefreshUrlQuota|Integer|刷新URL上限。|
|RefreshDirQuota|Integer|刷新目录上限。|
|RefreshUrlRemain|Integer|刷新URL余量。|
|RefreshDirRemain|Integer|刷新目录余量。|
|PreloadQuota|Integer|预热上限。|
|PreloadRemain|Integer|预热余量。|
|BlockQuota|Integer|封禁上限。|
|BlockRemain|Integer|封禁余量。|

## 示例 { .section}

请求示例：

```
https://cdn.aliyuncs.com?&Action=DescribeCdnUserQuota&<公共请求参数>

```

返回示例：

JSON格式：

```
{
    "DomainQuota" : 20,
    "RefreshUrlQuota" : 1000,
    "RefreshDirQuota" : 500,
    "RefreshUrlRemain" : 500,
    "RefreshDirRemain" : 300,
    "PreloadQuota" : 300,
    "PreloadRemain" : 100,
    "BlockQuota" : 100,
    "BlockRemain" : 100,
    "RequestId" : "BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23"
}
```

