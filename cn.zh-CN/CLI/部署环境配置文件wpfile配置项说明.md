# 部署环境配置文件wpfile配置项说明 {#concept_189195 .concept}

部署环境配置项包含了创建一个部署环境所需的全部信息。配置是可重复的，环境独占的资源比如导入的ECS实例不属于重复配置。

## 平台 {#section_gs6_8z0_ubd .section}

|配置路径|配置项|配置名|默认值|值域|描述|
|----|---|---|---|--|--|
|proxy|type|反向代理类型|nginx|\[nginx,apache\]|使用的反向代理类型，反向代理启动后将监听实例的80端口，请确保此端口不被其他程序占用，反向代理将把接收到的HTTP请求转发到应用的服务端口。|
|proxy.nginx|version|Nginx版本|1.14.2|1.14.2|使用的nginx版本，仅当反向代理类型为nginx时有效。|
|proxy.apache|version|Apache版本|2.4.6|2.4.6|使用apache版本，仅当反向代理类型为apache时有效。|

## 资源 {#section_24a_my6_9ns .section}

resources.network：网络配置

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|vpcOption|网络选项|\{"vpcId":"","vSwitches":\[\]\}| |部署环境使用的VPC和交换机，若选择多个交换机，Web+将在所选的交换机上均衡的分配ECS实例。可以在VPC控制台新建VPC和交换机。|

resources.ecs.autoScaling：实例配置

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|instanceType|实例规格|\["ecs.g5.large"\]| |部署环境使用的实例规格，Web+将使用所选择的规格创建ECS实例。可选择多个规格，当所选规格库存不足时，Web+将依据选择的顺序尝试创建，最多选择10种实例规格。|
|instanceNum|实例数量|1|\[0,100\]|使用的实例数量，WebPlus将依据此数量对部署环境进行扩容或缩容。|
|securityGroupIds|安全组|\[\]| |实例使用的安全组，最多选择5个安全组。|
|keyPairName|密钥对| | |密钥对，用于SSH登录，使用方法可参考使用SSH密钥对。|
|systemDiskSize|系统磁盘| | |系统盘大小（GB）|
|enableInternet|启用公网IP|true|\[true,false\]|是否启用公网IP，若启用，则该部署环境内的ECS实例都能从公网被访问，请注意安全配置；ECS实例提供的公网服务可能产生费用，请参考公网带宽计费。|
|instanceName|实例名称| | |自定义创建ECS实例的名称|
|scalingPolicy|主机回收模式|recycle|\[release,recycle\]|设置主机停机回收时的处理策略，release为释放配置，释放掉ECS实例所有的资源；recycle为停机回收模式，保留主机的磁盘，会产生一部分费用|
|userData|实例自定义数据| | |需要以 Base64 方式编码，原始数据最多为 16 KB。|
|systemDiskCategory|系统盘的磁盘类型|cloud\_efficiency|\[cloud,cloud\_efficiency,cloud\_ssd,ephemeral\_ssd\]|cloud：普通云盘cloud\_efficiency：高效云盘cloud\_ssd：SSD 云盘ephemeral\_ssd：本地 SSD 盘InstanceType 为系列 I 的规格且实例属于非 I/O 优化实例时，默认值：cloud。否则，默认值：cloud\_efficiency。|
|multiAzPolicy|多可用区伸缩组 ECS 实例扩缩容策略|BALANCE|\[PRIORITY,BALANCE\]|取值范围：PRIORITY：根据您定义的虚拟交换机（VSwitchIds.N）扩缩容。当优先级较高的虚拟交换机所在可用区无法创建 ECS 实例时，自动使用下一优先级的虚拟交换机创建 ECS 实例。BALANCE：在伸缩组指定的多可用区之间均匀分配 ECS 实例。如果由于库存不足等原因可用区之间变得不平衡，您可以通过 API RebalanceInstance 平衡资源。|
|internetChargeType|网络计费类型|PayByTraffic|\[PayByBandwidth,PayByTraffic\]|PayByBandwidth：按带宽计费。此时 InternetMaxBandwidthOut 即为所选的固定带宽值。PayByTraffic：按流量计费。此时 InternetMaxBandwidthOut 只是一个带宽上限，计费以发生的网络流量为依据。|
|internetMaxBandwidthIn|公网入带宽最大值|100|\[1,200\]|单位为 Mbps \(Mega bit per second\)，取值范围：1~200。如果您没有指定该参数，则入带宽将自动被设置为 200 Mbps。该参数在任何情况下都不涉及计费，实例的入数据流量是免费的。|
|internetMaxBandwidthOut|公网出带宽最大值|50|\[0,100\]|，单位为 Mbps \(Mega bit per second\)，取值范围：按带宽计费：0~100，如果您没有指定该参数，则出带宽将自动被设置为 0 Mbps。按流量计费：0~100。|
|ioOptimized|是否为 I/O 优化实例|true|\[true,false\]|是否为 I/O 优化实例|

resources.slb.internet：公网SLB配置

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|enable|启用公网SLB|true|\[true,false\]|是否启用公网SLB，如部署环境存在多个实例，可使用SLB来进行负载均衡，可以在SLB控制台创建或配置SLB。|
|slbId|公网SLB| | |使用已有的SLB实例或由Web+来自动代购SLB实例。|
|listenerPort|公网SLB监听端口|80|\[1,65535\]|公网SLB的监听端口，可以使用此端口从公网访问应用。|
|protocol|公网SLB协议|http|\[http,tcp\]|公网SLB使用的协议类型|
|forwardingRule|公网SLB转发规则| | |公网SLB使用的转发规则|
|bandwidth|监听的带宽峰值|-1|\[-1,5120\]|监听的带宽峰值。|
|loadBalancerSpec|负载均衡实例的规格|slb.s1.small|\[slb.s1.small,slb.s2.small,slb.s2.medium,slb.s3.small,slb.s3.medium,slb.s3.large\]|每个地域支持的规格不同。|
|internetChargeType|公网类型实例的付费方式|paybytraffic|\[paybybandwidth,paybytraffic\]|paybybandwidth：按带宽计费paybytraffic：按流量计费（默认值）。|
|healthCheckUrl|健康检查URl|/| | |

resources.slb.intranet：内网SLB配置

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|enable|启用内网SLB|true|\[true,false\]|是否启用内网SLB，如部署环境存在多个实例，可使用SLB来进行负载均衡，可以在SLB控制台创建或配置SLB。|
|slbId|内网SLB| | |使用已有的SLB实例或由Web+来自动代购SLB实例。|
|listenerPort|内网SLB监听端口|80|\[1,65535\]|内网SLB的监听端口，可以使用此端口从公网访问应用。|
|protocol|内网SLB协议|http|\[http,tcp\]|内网SLB使用的协议类型。|
|forwardingRule|内网SLB转发规则| | |内网SLB使用的转发规则。|
|bandwidth|监听的带宽峰值|-1|\[-1,5120\]|监听的带宽峰值。|
|bandwidth|监听的带宽峰值|-1|\[-1,5120\]|监听的带宽峰值。|
|loadBalancerSpec|负载均衡实例的规格|slb.s1.small|\[slb.s1.small,slb.s2.small,slb.s2.medium,slb.s3.small,slb.s3.medium,slb.s3.large\]|每个地域支持的规格不同。|
|internetChargeType|公网类型实例的付费方式|paybytraffic|\[paybybandwidth,paybytraffic\]|paybybandwidth：按带宽计费paybytraffic：按流量计费（默认值）。|

resources.rds：RDS配置

|配置项|配置名|有效值|默认值|描述|
|---|---|---|---|--|
|enable|是否开启|true / false|false|是否启用RDS。|
|imported|是否为导入|true / false|false|是否使用已有RDS。|
|rdsId|RDS ID|有效的RDS实例ID|无|RDS实例ID。在导入已有RDS场景下，需要提供此配置项来指明导入的RDS。|
|zoneId|可用区|有效的RDS可用区ID|无|RDS可用区ID。可通过RDS的DescribeRegions接口来获取有效的RDS可用区。|
|VSwitches|交换机列表|交换机ID|无|指定RDS所在可用区的交换机。|
|engine|数据库类型|数据库类型，取值：MySQL ；SQLServer ；PostgreSQL ；PPAS ；MariaDB 。|无|数据库类型。|
|engineVersion|数据库版本|数据库版本，取值：MySQL： 5.5/5.6/5.7/8.0 ；SQL Server：2008r2/2012/2012\_ent\_ha/2012\_std\_ha/2012\_web/2016\_ent\_ha/2016\_std\_ha/2016\_web/2017\_ent ；PostgreSQL： 9.4/10.0 ；PPAS： 9.3/10.0 ；MariaDB： 10.3 。|无|数据库版本。|
|storageType|存储类型|实例存储类型，取值：local\_ssd / ephemeral\_ssd ：本地SSD盘（推荐）；cloud\_ssd ：SSD云盘；cloud\_essd ：ESSD云盘。|无|存储类型。|
|storageSize|存储空间大小|整数|100|存储大小，单位G。|
|dbInstanceClass|实例规格|有效的实例规格|无|实例规格，有效值详见 实例规格表。|
|databaseName|库名|字符串|webplus|数据库名。|
|characterSetName|库字符集|字符集，取值：MySQL/MariaDB实例： utf8、gbk、latin1、utf8mb4 ；SQL Server实例：Chinese\_PRC\_CI\_AS、Chinese\_PRC\_CS\_AS、SQL\_Latin1\_General\_CP1\_CI\_AS、SQL\_Latin1\_General\_CP1\_CS\_AS、Chinese\_PRC\_BIN 。|MySQL/MariaDB实例：utf8mb4 ；SQL Server实例：Chinese\_PRC\_CI\_AS|字符集。|
|accountName|账号名|字符串|webplus|数据库账号。|
|accountPassword|账号密码|字符串|无|数据库账号密码。|
|category|类型|实例系列，取值： -   Basic：基础版
-   HighAvailability：高可用版
-   AlwaysOn：集群版
-   Finance：金融版（仅中国站支持）

 |无|数据库实例系列。|

## 应用 {#section_it7_4p9_9dd .section}

application.option：服务端口

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|port|服务端口|8080|\[1024,65535\]|应用启动后将使用此端口作为HTTP服务端口，可以使用从1024到65535之间的端口。|

application.healthCheck：健康检查配置

|配置项|配置名|默认值|值域|描述|
|---|---|---|--|--|
|type|健康检查类型|http|\[http, tcp\]|健康检查使用的协议类型，目前支持TCP和HTTP，Web+将定期发送健康检查请求到应用的服务端口以确定应用是否健康。|
|retryCount|健康检查重试次数|3|\[1,30\]|若健康检查重试超过此次数则判定为健康检查失败。|
|intervalSeconds|健康检查间隔|3|\[1,60\]|当一次检查失败时，到下次健康检查的间隔时长。|
|timeoutSeconds|健康检查超时时间|3|\[1,60\]|单次健康检查的超时时长。|

application.commands：操作命令

|配置项|配置名|描述|
|---|---|--|
|start|启动命令|设定启动应用使用的命令。|
|stop|停止命令|设定停止应用使用的命令。|

hooks：生命周期挂钩

|配置项|配置名|描述|
|---|---|--|
|prestart|启动前置命令|设定启动应用前执行的命令。|
|poststart|启动后置命令|设定启动应用后执行的命令。|
|prestop|停止前置命令|设定停止应用前执行的命令。|
|poststop|停止后置命令|设定停止应用后执行的命令。|
|postinit|初始化后置命令|设定初始化应用后执行的命令。|

application.jvmOpts： Java虚拟机参数

|配置项|配置名|描述|
|---|---|--|
|value|JVM参数|设定启动应用时所用的Java虚拟机参数。|

application.enviromentVariables：环境变量

|配置项|配置名|描述|
|---|---|--|
|value|环境变量|设置启动应用时所用的环境变量。|

