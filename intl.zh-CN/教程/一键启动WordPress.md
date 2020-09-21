---
keyword: [WordPress, CMS, 内容管理, 一键启动]
---

# 一键启动WordPress

WordPress是一种使用非常广泛的内容管理系统（CMS）。本文介绍如何使用Web+来一键启动一个WordPress站点。

## 在Web+控制台一键启动WordPress环境

在Web+控制台首页，您可以一键启动一个WordPress环境。

1.  登录[Web+控制台](http://webplus-intl.console.aliyun.com/)，并在页面左上角选择所属地域。

2.  在**概览**页的**最近更新的部署环境**区域的右上角单击**一键启动WordPress**。

3.  在**一键部署WordPress**页面设置环境信息。

    |参数|描述|
    |--|--|
    |应用名称|根据控制台提示输入您想创建的应用名称。|
    |应用描述|输入一段描述信息帮助您识别这个应用。|
    |使用共享存储空间|    -   开启开关使用共享OSS存储。创建该应用后，其下的所有部署环境需要使用OSS存储的地方（相关场景有上传部署包、收集日志和收集诊断信息等），都将存储于Web+提供的公共OSS。
    -   关闭开关后则将对应文件存储于您自己的OSS。 |
    |自定义部署环境信息|    -   开关关闭时您可按照低成本配置直接创建一个WordPress环境，部署环境名称与应用名称相同。
    -   开启开关后可自定义**部署环境名称**和**部署环境描述**。 |

4.  单击**确定**。

5.  在**操作清单**对话框查看变更清单，单击**确定**。

    之后将会出现成功创建应用和创建部署环境的页面提示。单击**查看部署环境日志**可进入创建的WordPress部署环境**变更事件**对话框，待变更完成后关闭对话框进入部署环境**概览**页。


## 访问部署的Web应用来安装配置WordPress

1.  在部署环境**概览**页单击**公网访问地址**访问创建的Web应用。

    ![部署环境概览页](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7335063951/p80749.png)

2.  进入WordPress配置页面，选择所要使用的语言，屏幕将会出现下图中显示的内容。

    ![WordPress首页](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7335063951/p80752.png)

3.  根据自己的业务需求完成后续的WordPress配置。


