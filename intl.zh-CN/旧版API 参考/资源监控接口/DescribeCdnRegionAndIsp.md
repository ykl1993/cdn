# DescribeCdnRegionAndIsp {#reference_whk_y2n_vdb .reference}

获取区域和运营商列表。

## 请求参数 {#section_onf_bfn_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeCdnRegionAndIsp|系统规定参数。取值：DescribeCdnRegionAndIsp|

## 返回参数 {#section_pgl_dfn_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|2387C335-932C-4E1E-862C-1C4363B6DE72|请求ID。|
|Regions| | |区域列表。|
|  └NameZh|String|辽宁省|中文名称。|
|  └NameEn|String|liaoning|英文名称。|
|Isps| | |运营商列表。|
|  └NameZh|String|联通|中文名称。|
|  └NameEn|String|unicom|英文名称。|

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeCdnRegionAndIsp&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "Isps":{
            "Isp":[
                {
                    "NameEn":"unicom",
                    "NameZh":"联通"
                },
                {
                    "NameEn":"tietong",
                    "NameZh":"铁通"
                },
                {
                    "NameEn":"telecom",
                    "NameZh":"电信"
                },
                {
                    "NameEn":"cernet",
                    "NameZh":"教育网"
                },
                {
                    "NameEn":"drpeng",
                    "NameZh":"鹏博士"
                },
                {
                    "NameEn":"mobile",
                    "NameZh":"移动"
                }
            ]
        },
        "Regions":{
            "Region":[
                {
                    "NameEn":"liaoning",
                    "NameZh":"辽宁省"
                },
                {
                    "NameEn":"guangxi",
                    "NameZh":"广西壮族自治区"
                },
                {
                    "NameEn":"anhui",
                    "NameZh":"安徽省"
                },
                {
                    "NameEn":"ningxia",
                    "NameZh":"宁夏回族自治区"
                },
                {
                    "NameEn":"jiangxi",
                    "NameZh":"江西省"
                },
                {
                    "NameEn":"guangdong",
                    "NameZh":"广东省"
                },
                {
                    "NameEn":"neimenggu",
                    "NameZh":"内蒙古自治区"
                },
                {
                    "NameEn":"aomen",
                    "NameZh":"澳门特别行政区"
                },
                {
                    "NameEn":"jiangsu",
                    "NameZh":"江苏省"
                },
                {
                    "NameEn":"tianjin",
                    "NameZh":"天津市"
                },
                {
                    "NameEn":"chongqing",
                    "NameZh":"重庆市"
                },
                {
                    "NameEn":"jilin",
                    "NameZh":"吉林省"
                },
                {
                    "NameEn":"shaanxi",
                    "NameZh":"陕西省"
                },
                {
                    "NameEn":"shanghai",
                    "NameZh":"上海市"
                },
                {
                    "NameEn":"sichuan",
                    "NameZh":"四川省"
                },
                {
                    "NameEn":"yunnan",
                    "NameZh":"云南省"
                },
                {
                    "NameEn":"xianggang",
                    "NameZh":"香港特别行政区"
                },
                {
                    "NameEn":"taiwan",
                    "NameZh":"台湾省"
                },
                {
                    "NameEn":"shandong",
                    "NameZh":"山东省"
                },
                {
                    "NameEn":"xizang",
                    "NameZh":"西藏自治区"
                },
                {
                    "NameEn":"hebei",
                    "NameZh":"河北省"
                },
                {
                    "NameEn":"qinghai",
                    "NameZh":"青海省"
                },
                {
                    "NameEn":"gansu",
                    "NameZh":"甘肃省"
                },
                {
                    "NameEn":"xinjiang",
                    "NameZh":"新疆维吾尔自治区"
                },
                {
                    "NameEn":"heilongjiang",
                    "NameZh":"黑龙江省"
                },
                {
                    "NameEn":"shanxi",
                    "NameZh":"山西省"
                },
                {
                    "NameEn":"hainan",
                    "NameZh":"海南省"
                },
                {
                    "NameEn":"zhejiang",
                    "NameZh":"浙江省"
                },
                {
                    "NameEn":"henan",
                    "NameZh":"河南省"
                },
                {
                    "NameEn":"fujian",
                    "NameZh":"福建省"
                },
                {
                    "NameEn":"guizhou",
                    "NameZh":"贵州省"
                },
                {
                    "NameEn":"hubei",
                    "NameZh":"湖北省"
                },
                {
                    "NameEn":"hunan",
                    "NameZh":"湖南省"
                },
                {
                    "NameEn":"beijing",
                    "NameZh":"北京市"
                }
            ]
        },
        "RequestId":"2387C335-932C-4E1E-862C-1C4363B6DE72"
    }
    ```


**异常返回示例**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```


