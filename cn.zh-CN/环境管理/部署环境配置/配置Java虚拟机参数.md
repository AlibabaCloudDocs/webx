# 配置Java虚拟机参数 {#concept_270235 .concept}

Java虚拟机（JVM ）参数用于在应用启动时配置容器的参数。正确配置这些参数有助于降低垃圾回收（GC）开销，从而缩短服务器响应时间并提高吞吐量。如果没有配置容器参数，默认由 JVM 分配。

## Java虚拟机简介 {#section_jwl_myi_y3b .section}

Java虚拟机（Java Virtual Machine，缩写为JVM），一种能够运行Java bytecode的虚拟机，以堆栈结构机器来进行实做。最早由太阳微系统所研发并实现第一个实现版本，是Java平台的一部分，能够运行以Java语言写作的软件程序。

Java虚拟机有自己完善的硬体架构，如处理器、堆栈、寄存器等，还具有相应的指令系统。JVM屏蔽了与具体操作系统平台相关的信息，使得Java程序只需生成在Java虚拟机上运行的目标代码（字节码），就可以在多种平台上不加修改地运行。通过对中央处理器（CPU）所执行的软件实现，实现能执行编译过的Java程序码（Applet与应用程序）。

## 设置JVM参数 {#section_mef_i21_xkg .section}

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**查看全部**。
3.  在**应用及部署环境**页面单击所选应用最左侧的 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163212/156048105547117_zh-CN.png)展开应用所关联的环境列表。

    **说明：** 在**概览**页会罗列4个最近更新的部署环境，如需管理的环境在该列表中，可以直接单击环境名称进入环境管理控制台。

4.  选择并单击部署环境名称进入部署环境**概览**页面。
5.  在左侧导航栏单击**配置**进入环境配置页面。
6.  在**应用**模块单击展开**Java虚拟机**，在输入框内设置JVM参数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223017/156048105548039_zh-CN.png)

7.  完成设置后可单击配置页面右上角的**变更配置**使更改生效。

