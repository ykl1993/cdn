# CDN子账户使用指南 {#concept_zk3_mr2_xdb .concept}

本文档提供给CDN域名资源组管理需求的客户，通过子账户+资源组授权实现不同部门之间资源的隔离操作，接入流程如下。

## 接入流程 {#section_vx5_zw2_xdb .section}

1.  登录企业控制台。

    **说明：** 资源组设置和子账号管理需要在企业控制台完成，设置好相应的资源组和权限后，子账号登录CDN控制台就会按照已定的规则进行有限的资源查看和操作，保证子账户间的操作和资源展示完全隔离。

    使用主账号登录[企业控制台](https://enterprise.console.aliyun.com/) （附：[企业控制台使用手册](https://help.aliyun.com/document_detail/59910.html)）。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3487_zh-CN.png)

2.  创建子账户。
    -   进入**人员管理**模块，初次进入需要创建目录,一个用户必须且只能归属于某一个目录下。
    -   创建目录后，可以在**人员管理** \> **用户管理**中创建子账户。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3488_zh-CN.png)

        **说明：** 根据业务需求还可以创建群组，统一管理。

3.  创建资源组 + 授权。

    进入**资源管理**模块，创建资源组，如下创建 **1号BU资源组**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3489_zh-CN.png)

    择需要管理的资源组，完成该组内的**资源**、**成员**和基础信息**设置**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3490_zh-CN.png)

    进入**资源管理** \> **资源** 实现加速域名分组设置，在筛选区选择产品CDN，勾选需要加入该资源组的加速域名，单击**转入**，完成资源组内加速域名设置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3491_zh-CN.png)

    进入**资源管理** \> **成员**完成子账户的授权，单击**新增成员**，可以选择需要管理本资源组的子账户，并完成策略授权，附：授权模板说明。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3492_zh-CN.png)

4.  使用子账号登录CDN控制台。

    登录地址： [http://signin.aliyun.com/<自定义域\>.onaliyun.com/login.htm](http://signin.aliyun.com/%3C%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%3E.onaliyun.com/login.htm)

    子账户登录后，可以选择展示当前子账户拥有权限的资源组，根据资源组罗列加速域名。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/3493_zh-CN.png)

    自账户支持 域名管理、监控、刷新和日志下载，其他操作同主账号完全一致，请参考 [快速入门](https://help.aliyun.com/document_detail/27112.html)。


## 附录 {#section_nmw_4y2_xdb .section}

当前RAM模板策略

1.  CDN管理授权：支持增删查改。

    ```
    {
      "Version": "1",
      "Statement": [
        {
          "Action": "cdn:*",
          "Resource": "*",
          "Effect": "Allow"
        }
      ]
    }
    ```

2.  CDN只读权限。

    ```
    {
      "Version": "1",
      "Statement": [
        {
          "Action": "cdn:Describe*",
          "Resource": "*",
          "Effect": "Allow"
        }
      ]
    }
    ```


