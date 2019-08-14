# 使用Spring Boot开发应用 {#concept_187795 .concept}

Spring Boot是一个轻量级框架，可以用来轻松地创建独立的、生产级的、基于Spring且能直接运行的应用。在本教程中，您将学习如何开发一个简单的Spring Boot应用，并将其部署到Web+。

## 准备工作 {#section_a97_8ey_o6k .section}

在进入本教程之前，请确保您已经安装并配置好了以下3个工具：

-   [IntelliJ IDEA](https://www.jetbrains.com/idea/)
-   [Maven](https://maven.apache.org/)
-   [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

## 步骤一：创建Demo工程 {#section_rip_fe9_g30 .section}

1.  启动IntelliJ IDEA。
2.  选择**File**-\>**New**-\>**Project**，新建一个工程。
3.  对项目进行配置并完成创建。
    1.  在左侧导航栏选择**Spring Initializr**，然后单击**Next**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156577172554605_zh-CN.png)

    2.  设置工程信息，设置完成后单击**Next**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172555209_zh-CN.png)

    3.  在**Dependencies**页面单击**Web**并勾选**Spring Web Starter**，然后单击**Next**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156577172555107_zh-CN.png)

    4.  输入工程名称，并单击**Finish**完成创建。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163218/156577172655109_zh-CN.png)

    5.  打开工程目录下的pom.xml文件，并在其中加入下图所示圈注部分的配置。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172655215_zh-CN.png)


## 步骤二：配置应用 {#section_dbh_0aj_6m0 .section}

1.  新建一个Controller。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172655220_zh-CN.png)

2.  单击调试按钮，启动应用。
3.  在浏览器中输入下图所示访问地址来访问应用。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172755221_zh-CN.png)


## 步骤三：构建可执行JAR {#section_76a_k57_k1i .section}

1.  单击右侧的**Maven**选项卡，在弹出的页面中单击**Execute Maven Goal**按钮。在弹出的对话框中输入package命令，然后单击**Execute**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172755271_zh-CN.png)

2.  打包完成后可在工程的target目录下看到一个Jar包（如demo-0.0.1-SNAPSHOT.jar），接下来需要将这个应用程序部署到web+应用中。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172755274_zh-CN.png)


## 步骤四：创建应用并完成部署 {#section_ptv_k64_tft .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为Java，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172755338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的demo-0.0.1-SNAPSHOT.jar，设置部署包版本后单击**完成创建**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172855348_zh-CN.png)

5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156577172855358_zh-CN.png)


## 更多信息 {#section_say_dd1_jqz .section}

-   在Web+控制台快速部署应用的视频演示请参见[在Web+控制台创建应用和部署环境](../DNWEBX19101931/ZH-CN_TP_519470_V3.dita)。
-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   完成应用托管之后的应用的管理操作请参见[应用详情概览](../DNICMS19100635/ZH-CN_TP_163214_V1.dita)。
-   管理应用所在的部署环境的操作请参见[部署环境概览](../DNICMS19100636/ZH-CN_TP_163212_V1.dita)。

