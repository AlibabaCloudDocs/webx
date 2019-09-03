# 负载均衡SLB {#concept_270228 .concept}

在Web+中，如果部署环境存在多个ECS实例，可以使用负载均衡SLB实现多个实例间的流量分配。使用负载均衡进行流量分发，可以扩展应用对外的服务能力，消除单点故障并提升应用系统的可用性。

## 背景信息 {#section_brx_49i_19b .section}

在Web+中选择代购SLB，那么Web+将会自动为您购买新的SLB并配置监听端口和转发规则，您只需专注于业务逻辑，而不用关注底层SLB配置细节。代购的SLB规格默认为slb.s1.small，付费模式为按量付费。

如果您在使用Web+之前已经创建过SLB，那么您可以在Web+中选择导入模式，选择已创建的SLB，并配置监听端口和服务器组。配置完成后Web+会自动把部署环境中的ECS机器同步到选择的服务器组中。

在Web+中您可以配置公网负载均衡实现公网访问；也可以配置内网负载均衡为应用提供一个仅VPC内能访问的入口，保证同VPC内其他应用能访问该应用。公网负载均衡和内网负载均衡的配置步骤几乎一致，本文档以公网负载均衡的配置过程作为示例。

## 代购负载均衡SLB {#section_fa4_2fj_x6e .section}

1.  在部署环境配置页面展开**公网负载均衡SLB**。
2.  打开**启用公网SLB**开关。
3.  **实例来源**选择为**代购**。
4.  输入**SLB监听端口**。

    SLB实例的监听端口，用户可以使用此端口从公网访问应用服务。在代购模式下，Web+将帮助您创建和维护该端口。

5.  设置**SLB协议**。

    SLB协议是为您服务所提供的流量协议，包含TCP和HTTP协议。如果设置SLB协议为HTTP，可以设置转发策略，这样当HTTP流量满足了转发规则之后，才会被路由到当前部署环境的实例上。

6.  设置**SLB转发策略**（仅当选择HTTP协议时需设置）。

    转发规则的格式为Host+Path，Host或Path需至少配置一项。下面的转发规则均为有效设置：

    -   www.taobao.com/test
    -   www.taobao.com
    -   /test

## 导入负载均衡SLB {#section_pgi_o7j_2pi .section}

1.  在部署环境配置页面展开**公网负载均衡SLB**。
2.  打开**启用公网SLB**开关。
3.  **实例来源**选择为**导入**。
4.  在**SLB实例**列表中选择一个已有的SLB实例。
5.  输入**SLB监听端口**。

    SLB实例的监听端口，用户可以使用此端口从公网访问应用服务。在导入模式下，此端口仅用来生成公网访问地址，请确保该端口与所选服务器组关联的监听端口一致。

6.  设置**SLB服务器组类型**。
    -   **默认服务器组**：用来接收前端请求的ECS实例。如果没有设置虚拟服务器组，则默认将请求转发至默认服务器组中的ECS。
    -   **虚拟服务器组**：选择一个虚拟服务器组，除选择已有虚拟服务器组外，您还可单击**创建虚拟服务器组**来创建分组，然后单击虚拟服务器组ID跳转到SLB控制台配置监听端口和转发规则。

        当您需要将不同的请求转发到不同的后端服务器上时，或需要通过域名和URL进行请求转发时，可以选择使用虚拟服务器组。

        在部署环境进行扩缩容的时候，Web+会自动将ECS实例同步到所选的虚拟服务器组中。


## 关闭负载均衡SLB {#section_t2j_30s_i8d .section}

当您关闭SLB时，Web+将会采取以下策略进行释放：

-   **代购SLB**：关闭SLB功能后，Web+将会清除当前环境的虚拟服务器组机器、转发规则和监听，并释放SLB实例；但如果此SLB实例当前被其他服务使用，那么Web+将会清除当前环境的虚拟服务器组机器、转发规则和监听，但不会释放该SLB实例。
-   **导入SLB**：Web+会在该SLB的服务器组中清除当前部署环境的ECS实例，不会释放SLB实例。

## 使用CLI配置SLB {#section_8q2_hhi_3dr .section}

CLI配置SLB需要通过Wpfile文件来进行，您可以通过wpctl dump命令来获取部署环境的Wpfile文件。您可以增加、修改或删除SLB的配置项，然后通过apply命令使其生效。

Wpfile文件中公网SLB配置项归类在**resources.slb.internet**下，内网SLB配置项归类在**resources.slb.intranet**下。公网SLB和内网SLB具有同样的配置项，配置项含义为：

|配置项|有效值|默认值|描述|
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

