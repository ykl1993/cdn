# RefreshObjectCaches {#reference_srr_cyc_5db .reference}

刷新节点上的文件内容。

-   刷新指定URL内容至Cache节点，支持URL批量刷新。
-   支持post请求，参数用form表单。

限制条件：

-   同一个 ID 每天最多提交预热刷新类请求数量如下：
    -   URL：2000条。
    -   目录：100个。
-   刷新预热类接口包含RefreshObjectCaches刷新接口和PushObjectCache 预热接口。

## 请求参数 {#section_rxs_wnz_5db .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|RefreshObjectCaches| 系统规定参数。取值：

 RefreshObjectCaches

 |
|ObjectPath|String|是|abc.com/image/1.png| 输入示例：abc.com/image/1.png，多个URL之间需要用换行符（\\n或\\r\\n）分隔。

 |
|ObjectType|String|否|File| 可选，刷新的类型，其值可以为File或Directory。

 默认值：File。

 |

**说明：** 当ObjectType值为Directory时，ObjectPath结尾需加符号/。

## 返回参数 {#section_vkr_f4z_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RefreshTaskId|String|704222904| 刷新返回的任务ID，多个任务ID用逗号（半角）分隔。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| 请求ID。

 |

## 示例 {#section_fb4_44z_5db .section}

**请求示例**

```
https://cdn.aliyuncs.com?&Action=RefreshObjectCaches&ObjectPath=test.test.com/test.txt&ObjectType=File&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RefreshTaskId":"704222904",
        "RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
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


