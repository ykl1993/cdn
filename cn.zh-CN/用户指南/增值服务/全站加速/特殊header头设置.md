# 特殊header头设置 {#concept_lcl_qtx_wdb .concept}

## 功能介绍 {#section_ck3_stx_wdb .section}

根据Header中的Cache-Control字段，选择是否动态加速。Header相应头的Cache-Control内容符合配置中任一规则就强制开启动态加速，不再检查其余配置。

## 配置引导 {#section_g1w_stx_wdb .section}

选择**域名管理** \> **域名配置页面** \> **动静态加速规则设置**：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5164/15404695613244_zh-CN.png)

选择**特殊Header头设置** \> **设置要强制开启动态加速的Cache-Control规则：**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5164/15404695613245_zh-CN.png)

**说明：** 例如：设置了规则为 no-cache，则所有响应头中的Cache-Control中带no-cache的资源都强制开启动态加速，不缓存在边缘节点上。

