# 配置SLB {#concept_270228 .concept}

SLB（Server Load Balancer）是阿里云提供的负载均衡服务，可以对多台云服务器进行流量分发。使用负载均衡进行流量分发，可以扩展应用系统对外的服务能力，消除单点故障并提升应用系统的可用性。

## 背景信息 {#section_k0a_7pa_xg3 .section}

如果您在使用Web+之前已经创建过SLB，那么您可以选择使用该SLB；您也可以选择不复用，那么Web+将会自动为您创建新的SLB并进行配置。新SLB的规格将为slb.s1.small，付费模式为按量付费。

Web+ SLB当前支持HTTP协议和TCP协议的流量转发。对于HTTP流量的转发，您可以设置转发规则，当该监听的流量满足了转发规则才会转发到相应的部署环境；转发规则适用于多个部署环境（或多个应用）复用同一个HTTP监听端口的场景。

## 进入SLB配置页面 {#section_lsg_3ed_lx4 .section}

在创建新部署环境和修改正在运行的部署环境配置时，您都可以对SLB的配置进行修改。

创建应用及部署环境时

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**，根据页面提示完成**应用基本信息**和**部署环境信息**设置后进入部署环境**配置**页面。
3.  在部署环境**配置**页面选择**预设配置**模式为**自定义**。
4.  在展开的配置页面上，选择资源分类下的**公网SLB**或**私网SLB**进行配置。
5.  点击**完成创建**将新建部署环境并使SLB配置生效。

选择已有应用创建部署环境时

1.  在**概览**页**最近更新的部署环境**区域的右上角单击**查看全部**。
2.  在**应用及部署环境**页面要新建环境的应用的ID。
3.  在**部署环境管理**页面单击**创建部署环境**所在的卡片，配置部署环境信息后进入**配置**页面。
4.  在部署环境**配置**页面选择**预设配置**模式为**自定义**。
5.  在展开的配置页面上，选择资源分类下的**公网SLB**或**内网SLB**并进行配置。
6.  点击**完成创建**将新建部署环境并使SLB配置生效。

更改部署环境时

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**查看全部**。
3.  在**应用及部署环境**页面单击所选应用最左侧的 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163212/156048103547117_zh-CN.png)展开应用所关联的环境列表。

    **说明：** 在**概览**页会罗列4个最近更新的部署环境，如您想管理的环境在该列表中，可以直接单击环境名称进入环境管理控制台。

4.  选择并单击部署环境名称进入部署环境**概览**页面。
5.  在左侧导航栏单击**配置**进入环境配置页面。
6.  在展开的配置页面上，选择资源分类下的**公网SLB**或**内网SLB**进行配置。
7.  点击**变更配置**将更新部署环境并使SLB配置生效。

## SLB配置项说明 {#section_515_fqf_kto .section}

启用/关闭SLB

公网SLB和内网SLB均有开关来表示是否启用。下图以启用公网SLB为例展示说明。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223010/156048103548335_zh-CN.png)

当启用SLB时，您有两种方式来使用SLB：

-   使用已有SLB：您可以通过开启开关选择**使用已有SLB**来复用SLB，在展开的已有SLB列表内选择一个已有SLB实例进行配置。Web+会检测您当前的监听转发配置和已有的配置是否冲突，如果冲突为了避免损坏您的已有服务，Web+的配置变更会失败，并且提示您配置冲突。
-   创建新的SLB：如您关闭开关选择**不使用已有SLB**，Web+将会自动为您创建新的SLB。新SLB的规格为`slb.s1.small`，付费模式为按量付费。

当您关闭SLB时，Web+将会采取如下策略：

-   如创建SLB时采用了**使用已有SLB**方式：Web+将会清除当前环境的虚拟服务器组机器、转发规则和监听，但不会回收您的SLB实例。
-   如创建SLB时采用了**创建新的SLB**方式：Web+将会清除当前环境的虚拟服务器组机器、转发规则和监听，如果此SLB实例当前没有其他正在监听的流量和后端机器，那么Web+会释放该SLB实例，否则不会进行释放。

监听端口、协议及转发规则

您可以设置当前环境在SLB上的监听端口、协议和转发规则。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223010/156048103548336_zh-CN.png)

选择了SLB协议后，SLB监听器会使用该协议将端口传入的流量路由到当前环境的实例上。如果您选择了协议为HTTP，那么可以设置转发规则；当HTTP流量满足了转发规则之后，才会被路由到当前环境的实例上。转发规则的格式为**Host+Path**，Host或Path需至少配置一项。下面的转发规则均为有效设置：

-   www.taobao.com/test
-   www.taobao.com
-   /test

## 使用CLI配置SLB {#section_8q2_hhi_3dr .section}

CLI配置SLB需要通过Wpfile文件来进行，您可以通过wpctl dump命令来获取部署环境的Wpfile文件。您可以增加、修改或删除SLB的配置项，然后通过apply命令使其生效。

Wpfile文件中公网SLB配置项归类在**resources.slb.internet**下，内网SLB配置项归类在**resources.slb.intranet**下。公网SLB和内网SLB具有同样的配置项，配置项含义为：

|分类|配置项|有效值|默认值| |
|--|---|---|---|--|
|resources.slb.internet 或resources.slb.intranet|enable|true/false|false|是否启用SLB。|
|slbId|有效的slbId|无|当设置此值时，Web+将会复用此SLB，并根据您的配置参数对该SLB进行配置，以将特定流量转发到当前的部署环境的实例。|
|internetChargeType| -   paybytraffic
-   paybybandwidth

 |paybytraffic|计费方式，paybytraffic为按流量计费，paybybandwidth为按带宽计费|
|loadBalancerSpec| -   slb.s1.small
-   slb.s2.small
-   slb.s2.medium
-   slb.s3.small
-   slb.s3.medium
-   slb.s3.large

 |slb.s1.small|SLB实例规格|
|bandwidth|整数|-1|带宽峰值，当计费方式为paybybandwidth时有效|
|listenerPort|整数|80|监听端口|
|protocol| -   HTTP
-   TCP

 |HTTP|监听协议|
|forwardingRule|格式为Host+Path，Host或Path其中之一可以为空，但不能同时为空。例如，下面的转发规则都是合法的： `www.taobao.com/test`、 `www.taobao.com`、`/test`|无|转发规则，当监听协议为HTTP时有效。|
|healthCheckUrl|URL路径|无|健康检查的URL路径|

