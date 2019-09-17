# 使用Web+部署Tomcat应用 {#concept_189189 .concept}

Web+的Tomcat技术栈是一组环境配置，用于Tomcat Web容器中运行的Java Web应用。在本教程中，您将学习如何开发一个简单的Tomcat应用，并将其部署到Web+。

## 准备工作 {#section_4zx_96m_ot4 .section}

在进入本教程之前，请确保您已经安装并配置好了以下工具和容器：

-   [IntelliJ IDEA](https://www.jetbrains.com/idea/)
-   [Maven](https://maven.apache.org/)
-   [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)
-   [Tomcat 8.5及以上版本](http://tomcat.apache.org/)

## 步骤一：创建Tomcat Demo工程 {#section_1fj_2jt_3fu .section}

1.  启动IntelliJ IDEA。
2.  选择**File**-\>**New**-\>**Project**，新建一个工程。
3.  选择**Spring Initializr**，然后单击**Next**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115254605_zh-CN.png)

4.  输入工程信息，并选择打包方式为War，设置完成后单击**Next**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115254606_zh-CN.png)

5.  在**Dependencies**页面单击**Web**并勾选**Spring Web Starter**，然后单击**Next**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115255107_zh-CN.png)

6.  输入工程名称，并单击**Finish**完成创建。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115255109_zh-CN.png)


## 步骤二：配置应用 {#section_rnd_uyw_q3n .section}

1.  新建一个Controller类。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115259438_zh-CN.png)

2.  参照以下步骤，配置本地运行环境。
    1.  在项目页面选择**DemoApplication**\> **Edit Configurations**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115259439_zh-CN.png)

    2.  在页面左上角单击**+**，然后选择**Tomcat Server** \> **Local**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359443_zh-CN.png)

    3.  在Server页签配置8.5及以上版本的Tomcat。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359517_zh-CN.png)

    4.  在Deployment页签选择**+** \> **Artifacts**配置部署方式。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359519_zh-CN.png)

    5.  在**Select Artifacts to Deploy**对话框中选择部署方式为**war exploded**，然后单击**OK**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359532_zh-CN.png)

3.  单击调试、Run或Debug按钮，启动应用。
4.  在浏览器中输入http://localhost:8080来访问应用。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359533_zh-CN.png)


## 步骤三：打包应用 {#section_dra_zmn_7o2 .section}

1.  单击右侧的**Maven**选项卡，在弹出的页面中选择**Demo** \> **Lifecycle** \> **Package**进行打包。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359534_zh-CN.png)

2.  打包完成后可在工程的target目录下看到一个war包（如demo-0.0.1-SNAPSHOT.war），接下来需要将这个应用程序部署到Web+应用中。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156800115359535_zh-CN.png)


## 步骤四：创建应用并完成部署 {#section_mzo_ztw_fct .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为Tomcat，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217610/156800115358943_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的demo-0.0.1-SNAPSHOT.war，设置部署包版本后单击**完成创建**。
5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156800115358300_zh-CN.png)


## 连接数据库 {#section_bzu_owm_mej .section}

Tomcat类型的应用程序的连接数据库方法同Java类型的应用程序的访问数据库方式基本一致，具体操作请参见[向Java应用的部署环境中添加RDS实例](ZH-CN_TP_161339.dita)，连接数据库的方法示例可参考部署包[alibabacloud-webplus-tomcat-demo](https://github.com/aliyun/alibabacloud-webplus-tomcat-demo)。

## 更多信息 {#section_pyx_lxh_rp7 .section}

-   在Web+控制台快速部署应用的视频演示请参见[在Web+控制台创建应用和部署环境](../DNWEBX19101931/ZH-CN_TP_519470_V3.dita)。
-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   完成应用托管之后的应用的管理操作请参见[应用详情概览](../DNICMS19100635/ZH-CN_TP_163214_V1.dita)。
-   管理应用所在的部署环境的操作请参见[部署环境概览](../DNICMS19100636/ZH-CN_TP_163212_V1.dita)。

