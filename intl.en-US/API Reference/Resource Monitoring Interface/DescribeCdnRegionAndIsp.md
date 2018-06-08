# DescribeCdnRegionAndIsp {#reference_whk_y2n_vdb .reference}

Obtain a list of regions and carriers.

## Request parameters {#section_onf_bfn_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeCdnRegionAndIsp|The name of this interface. Value: DescribeCdnRegionAndIsp|

## Return parameters {#section_pgl_dfn_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|2387C335-932C-4E1E-862C-1C4363B6DE72|The ID of the request.|
|Regions| | |Regions list.|
|  └NameZh|String|Liaoning province.|Chinese name.|
|  └NameEn|String|liaoning|English name.|
|Isps| | |ISPs list.|
|  └NameZh|String|Unicom|Chinese name.|
|  └NameEn|String|unicom|English name.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeCdnRegionAndIsp&Public Request Parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Isps":{
            "Isp":[
                
                    "NameEn":"unicom",
                    "NameZh":"Unicom"
                
                
                    "NameEn":"tietong",
                    "NameZh":"Tietong"
                
                
                    "NameEn":"telecom",
                    "NameZh":"Telecom"
                
                
                    "NameEn":"cernet",
                    "NameZh":"Cernet"
                
                
                    "Nameen": "drpeng ",
                    "NameZh":"Dr PENG"
                
                
                    "NameEn":"mobile",
                    "NameZh":"Mobile"
                
            
        
        "Regions":{
            "Region":[
                
                    "NameEn":"liaoning",
                    "NameZh":"Liaoning province"
                
                
                    "NameEn":"guangxi",
                    "NameZh":"Guangxi Zhuang Autonomous Region"
                
                
                    "NameEn":"anhui",
                    "NameZh":"Anhui province"
                
                
                    "NameEn":"ningxia",
                    "NameZh":"Ningxia Hui Autonomous Region"
                
                
                    "NameEn":"jiangxi",
                    "NameZh":"Jiangxi province"
                
                
                    "NameEn":"guangdong",
                    "NameZh":"Guangdong province"
                
                
                    "NameEn":"neimenggu",
                    "NameZh":"Innter Mongolia Autonomous Region"
                
                
                    "NameEn":"aomen",
                    "NameZh":"Macao Special Administrative Region"
                
                
                    "NameEn":"jiangsu",
                    "NameZh":"Jiangsu province"
                
                
                    "NameEn":"tianjin",
                    "NameZh":"The city of Tianjin"
                
                
                    "NameEn":"chongqing",
                    "NameZh":"The city of Chongqing"
                
                
                    "Nameen": "Jelin ",
                    "NameZh":"Jilin province"
                
                
                    "NameEn":"shaanxi",
                    "NameZh":"Shaanxi province"
                
                
                    "NameEn":"shanghai",
                    "NameZh":"The city of Shanghai"
                
                
                    "NameEn":"sichuan",
                    "NameZh":"Sichuan province"
                
                
                    "NameEn":"yunnan",
                    "Namezh": "Yunnan Province"
                
                
                    "Nameen": "Xianggang ",
                    "NameZh":"Hong Kong Special Administrative Region"
                
                
                    "NameEn":"taiwan",
                    "NameZh":"Taiwan province"
                
                
                    "NameEn":"shandong",
                    "NameZh":"Shandong province"
                
                
                    "NameEn":"xizang",
                    "NameZh":"Tibet Autonomous Region"
                
                
                    "NameEn":"hebei",
                    "NameZh":"Hebei province"
                
                
                    "NameEn":"qinghai",
                    "NameZh":"Qinghai province"
                
                
                    "NameEn":"gansu",
                    "Namezh": "Gansu Province"
                
                
                    "NameEn":"xinjiang",
                    "NameZh":"Xinjiang Uygur Autonomous Region"
                
                
                    "NameEn":"heilongjiang",
                    "NameZh":"Heilongjiang province"
                
                
                    "NameEn":"shanxi",
                    "NameZh":"Shanxi province"
                
                
                    "NameEn":"hainan",
                    "NameZh":"Hainan province"
                
                
                    "NameEn":"zhejiang",
                    "NameZh":"Zhejiang province"
                
                
                    "NameEn":"henan",
                    "NameZh":"Henan province"
                
                
                    "Nameen": "Fujian ",
                    "NameZh":"Fujian province"
                
                
                    "NameEn":"guizhou",
                    "NameZh":"Guizhou province"
                
                
                    "NameEn":"hubei",
                    "NameZh":"Hubei province"
                
                
                    "NameEn":"hunan",
                    "NameZh":"Hunan province"
                
                
                    "NameEn":"beijing",
                    "NameZh":"The city of Beijing"
                
            
        
        "RequestId":"2387C335-932C-4E1E-862C-1C4363B6DE72"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```


