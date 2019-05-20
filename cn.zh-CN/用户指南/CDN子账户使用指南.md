# CDN子账户使用指南 {#task_261642 .task}

针对有CDN域名资源组管理需求的客户，可以通过子账户+资源组授权的方式实现不同部门之间资源的隔离操作。

1.  使用主账号登录[企业控制台](https://enterprise.console.aliyun.com/)，关于企业控制台的使用请参见[企业控制台使用手册](https://help.aliyun.com/document_detail/59910.html)。 

    **说明：** 资源组设置和子账号管理需要在企业控制台完成，设置好相应的资源组和权限后，子账号登录CDN控制台就会按照已定的规则进行有限的资源查看和操作，保证子账户间的操作和资源展示完全隔离。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743487_zh-CN.png)

2.  创建子账户。 
    1.  进入**人员目录**模块，首次进入需要创建目录，一个用户只能归属于某一个目录下。
    2.  创建目录后，您可以在**人员目录** \> **用户管理**中创建子账户。 

        根据业务需求，您还可以通过群组管理功能创建群组，统一管理子账户。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743488_zh-CN.png)

3.  创建资源组。 
    1.  进入**资源管理**模块，单击**新建资源组**，创建资源组**测试1**如下： 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743489_zh-CN.png)

    2.  选择需要管理的资源组，完成该组内的**资源管理**、**权限管理**和基本信息**设置**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743490_zh-CN.png)

    3.  单击**资源管理**，选择产品类型为**CDN共享带宽**，选择需要加入该资源组的加速域名，单击**转入资源** ，完成资源组内加速域名设置。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743491_zh-CN.png)

4.  授权。**权限管理**完成子账户的授权，单击**新增授权**，您可以选择需要管理本资源组的子账户，并完成策略授权。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743492_zh-CN.png)

    当前RAM模板策略

    -   AliyunCDNFullAccess：CDN管理授权，支持增删查改。

        ``` {#codeblock_tc1_cir_0y3}
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

    -   AliyunCDNReadOnlyAccess：CDN只读权限。

        ``` {#codeblock_16q_58d_6bo}
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

5.  使用子账号登录CDN控制台。登录地址： [http://signin.aliyun.com/<自定义域\>.onaliyun.com/login.htm](http://signin.aliyun.com/%3C%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%3E.onaliyun.com/login.htm) 

    子账户登录后，可以选择展示当前子账户拥有权限的资源组，根据资源组罗列加速域名。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15583404743493_zh-CN.png)

    子账户支持域名管理、监控、刷新和日志下载，其他操作同主账号完全一致，请参见[快速入门](https://help.aliyun.com/document_detail/27112.html)。


