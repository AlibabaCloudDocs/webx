# 配置SLB {#concept_270228 .concept}

SLB（Server Load Balancer）是阿里云提供的负载均衡服务，可以对多台云服务器进行流量分发。使用负载均衡进行流量分发，可以扩展应用系统对外的服务能力，消除单点故障并提升应用系统的可用性。

## 背景信息 {#section_k0a_7pa_xg3 .section}

如果您在使用Web+之前已经创建过SLB，那么您可以导入该SLB，并提供默认服务器组或虚拟服务器组，web+将会自动把环境中的机器同步到该服务器组中。

您也可以选择代购SLB，那么Web+将会自动为您购买新的SLB并进行监听、转发规则和服务器组配置，让您只需要专注业务逻辑，而不用关注底层SLB配置细节。代购的SLB规格默认为slb.s1.small，付费模式为按量付费。

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
3.  在**应用及部署环境**页面单击所选应用最左侧的 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163212/156514846747117_zh-CN.png)展开应用所关联的环境列表。

    **说明：** 在**概览**页会罗列4个最近更新的部署环境，如您想管理的环境在该列表中，可以直接单击环境名称进入环境管理控制台。

4.  选择并单击部署环境名称进入部署环境**概览**页面。
5.  在左侧导航栏单击**配置**进入环境配置页面。
6.  在展开的配置页面上，选择资源分类下的**公网SLB**或**内网SLB**进行配置。
7.  点击**变更配置**将更新部署环境并使SLB配置生效。

## SLB配置项说明 {#section_515_fqf_kto .section}

启用/关闭SLB

公网SLB和内网SLB均有开关来表示是否启用。下图以启用公网SLB为例展示说明。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223010/156514846748335_zh-CN.png)

当启用SLB时，您有两种方式来使用SLB：

-   导入已有SLB：您可以选择导入已有SLB，并在展开的已有SLB列表内选择一个已有SLB实例，提供服务器组。Web+会将环境中的机器同步到该服务器组中。
-   代购新的SLB：如您选择代购SLB，Web+将会自动为您购买新的SLB并进行配置。新SLB的规格为slb.s1.small，付费模式为按量付费。

当您关闭SLB时，Web+将会采取如下策略：

-   如果该SLB为导入的：Web+会在该SLB的服务器组中清除当前环境的机器；
-   如果该SLB为代购的：Web+将会清除当前环境的虚拟服务器组机器、转发规则和监听，如果此SLB实例当前被其他服务使用，那么Web+不会释放该SLB实例，否则进行释放。

导入SLB

当您选择导入已有SLB后，您需要提供默认服务器组或虚拟服务器组。Web+会将环境中的机器同步到该服务器组中。

代购SLB

如您选择代购SLB，Web+将会自动为您购买新的SLB并进行监听端口、协议及转发规则配置。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223010/156514846754627_zh-CN.png)

监听端口为公网可访问的端口，SLB协议则为您服务所提供的流量协议（TCP或HTTP）。如果您选择了协议为HTTP，那么可以设置转发规则；这样当HTTP流量满足了转发规则之后，才会被路由到当前环境的实例上。转发规则的格式为Host+Path，Host或Path需至少配置一项。下面的转发规则均为有效设置：

-   www.taobao.com/test
-   www.taobao.com
-   /test

## 使用CLI配置SLB {#section_8q2_hhi_3dr .section}

CLI配置SLB需要通过Wpfile文件来进行，您可以通过wpctl dump命令来获取部署环境的Wpfile文件。您可以增加、修改或删除SLB的配置项，然后通过apply命令使其生效。

Wpfile文件中公网SLB配置项归类在**resources.slb.internet**下，内网SLB配置项归类在**resources.slb.intranet**下。公网SLB和内网SLB具有同样的配置项，配置项含义为：

|配置项|有效值|默认值| |
|---|---|---|--|
|enable|true/false|false|是否启用SLB。|
|imported|true/false|false|是否导入已有SLB。|
|importedGroupType|defaultGroup virtualGroup

 virtualGroup| |导入SLB的服务器组类型，defaultGroup为默认服务器组，virtualGroup为虚拟服务器组。|
|vServerGroupId|字符串| |虚拟服务器组ID。如果选择导入SLB且服务器组类型为虚拟服务器组时，那么需要提供虚拟服务器组ID。|
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

