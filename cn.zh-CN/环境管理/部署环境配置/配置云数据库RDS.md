# 配置云数据库RDS {#concept_1095990 .concept}

Web+提供了对云数据库RDS资源的编排功能，通过配置数据库类型、数据库版本和存储类型等参数可实现将RDS实例添加至您的部署环境。

## 背景信息 {#section_476_l52_53j .section}

您可以通过Web+代购RDS实例或导入已有RDS实例来使用RDS。为保障数据安全性，在Web+内释放部署环境时不会自动释放RDS实例，您可以登录[RDS控制台](https://rdsnext.console.aliyun.com)进行数据备份及实例释放操作。

为保障数据安全性，Web+使用阿里云[KMS服务](https://www.aliyun.com/product/kms)来加密您的数据库秘钥，Web+为您创建的KMS秘钥是免费的。KMS服务API调用每位用户每个月有20000次免费额度，您在Web+上每次变更会调用2~3次API，因此免费额度可以支持您每月进行6000多次发布。当KMS API使用量超出后，将会收取0.6元/万次的费用。

## 进入云数据库RDS配置页面 {#section_txm_5v5_lmd .section}

在创建新部署环境和修改正在运行的部署环境配置时，您都可以对云数据库RDS的配置进行修改。

创建应用及部署环境时

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**，根据页面提示完成**应用基本信息**和**部署环境信息**设置后进入部署环境**配置**页面。
3.  在部署环境**配置**页面选择**预设配置**模式为**自定义**。
4.  在展开的配置页面上，选择资源分类下的**云数据库RDS**并进行配置。
5.  单击**完成创建**将新建部署环境，同时RDS配置将生效。

选择已有应用创建部署环境时

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**查看全部**。
3.  在**应用及部署环境**页面单击要新建环境的应用的ID。
4.  在应用详情**概览**页面右上角单击**创建部署环境**，设置部署环境信息后进入**配置**页面。
5.  在部署环境**配置**页面选择**预设配置**模式为**自定义**。
6.  在展开的配置页面上，选择资源分类下的**云数据库RDS**并进行配置。
7.  单击**完成创建**将新建部署环境，同时RDS配置项将生效。

更改部署环境时

1.  登录[Web+控制台](https://webplus.console.aliyun.com)。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**查看全部**。
3.  在**应用及部署环境**页面单击所选应用最左侧的 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163212/156334833147117_zh-CN.png)展开应用所关联的环境列表。
4.  选择并单击部署环境名称进入部署环境**概览**页面。
5.  在左侧导航栏单击**配置**进入环境配置页面。
6.  在展开的配置页面上，选择资源分类下的**云数据库RDS**并进行配置。
7.  单击**变更配置**将更新部署环境，同时RDS配置将生效。

## RDS配置项说明 {#section_34u_0rc_4ds .section}

开启RDS

打开**开启**开关即可开启RDS功能。

开启RDS后，您有两种方式来使用SLB：

-   **代购RDS实例**：该选项将新建RDS实例，那么Web+将会自动为您代购RDS实例并进行数据库、账号及密码配置。Web+为您代购的RDS实例默认使用按量付费模式，在代购流程执行完毕后，您可以登录[RDS控制台](https://rdsnext.console.aliyun.com)将Web+代购的RDS实例调整为包年包月付费模式。RDS的计费方式与收费项可参考[计费方式与收费项](../../SP_60/DNMYSQ1864174/ZH-CN_TP_7805_V41.dita)。
-   **导入RDS实例**：如果您在使用Web+之前已经创建过RDS实例，那么您可以直接导入RDS实例进行使用。使用已有RDS实例时您无需提供实例规格、数据库类型及版本、存储类型及大小等需在代购RDS时需配置的参数。

关闭RDS

关闭开关即可关闭RDS功能。

**注意**：当您关闭RDS时，为保证数据安全性，Web+不会自动释放RDS实例，您可以登录[RDS控制台](https://rdsnext.console.aliyun.com)进行数据备份及实例释放操作。

数据库类型及版本

RDS支持创建MySQL、SQL Server、PostgreSQL、PPAS和MariaDB TX类型数据库引擎，每种类型数据库引擎都有若干种版本可以选择，您可根据自己需要来选取相应数据库引擎。关于各个引擎的介绍，可参见[数据库引擎](https://help.aliyun.com/document_detail/26174.html)。

系列

云数据库RDS的实例包括四个系列，具体介绍可参见[RDS产品系列概述](https://help.aliyun.com/document_detail/55665.html) 

-   **基础版**：单节点实例，采用计算与存储分离的架构，可实现超高的性价比。
-   **高可用版**：采用一主一备的经典高可用架构，适合80%以上的用户场景。
-   **集群版**：适用于SQL Server 2017企业版，基于AlwaysOn技术实现，最大支持一主一备高可用架构和七个只读实例，支持横向扩展集群读能力。 购买时默认为高可用架构（仅包括主实例和备实例，没有只读实例）。
-   **金融版**：采用一主两备的三节点架构，通过多副本同步复制，确保数据的强一致性，提供金融级的可靠性。

存储类型及大小

为满足不同场景的需求，云数据库RDS提供三种数据存储类型，关于存储类型的介绍请参见[存储类型](https://help.aliyun.com/document_detail/69795.html?spm=a2c4g.11186623.2.20.216c3189CC7yOG) 

-   **本地SSD盘（推荐）**：本地SSD盘是指与数据库引擎位于同一节点的SSD盘。将数据存储于本地SSD盘，可以降低I/O延时。
-   **SSD云盘**：是指基于分布式存储架构的弹性块存储设备。将数据存储于SSD云盘，即实现了计算与存储分离。
-   **ESSD云盘**：增强型（Enhanced）SSD云盘，是阿里云全新推出的超高性能云盘产品。ESSD云盘基于新一代分布式块存储架构，结合25GE网络和RDMA技术，为您提供单盘高达100万的随机读写能力和更低的单路时延能力。

选择完存储类型后，您可以设置存储空间的大小。

可用区及交换机

可用区是指在某个地域内拥有独立电力和网络的物理区域，交换机则指定在相应可用区内RDS所在的交换机。在同一地域内多个可用区采用高速链路互通，您可以选择将RDS与应用软件的ECS创建在同一可用区或不同的可用区，因为同一地域的不同可用区之间没有实质性区别。

RDS实例规格

RDS实例规格分为通用型和独享型，关于各个规格的介绍请参见[实例规格族](https://help.aliyun.com/document_detail/57184.html)。

-   **通用型**：RDS独享被分配的内存和I/O资源，与同一物理机上的其他通用型实例共享CPU和存储资源；
-   **独享型**：RDS具有完全独享的CPU、内存、存储和I/O资源，性能长期稳定，不会因为物理机上其它实例的行为而受到影响；独享型的顶配是**独占物理机型**，也称为独占主机型，完全独占一台物理机的所有资源。

数据库

您需要在Web+上输入数据库库名。在代购场景下，如果RDS实例上没有此数据库，Web+将会自动为您创建；在导入已有RDS场景下，您需要自己保证该RDS实例上存在相应的数据库。

数据库账号及密码

您需要在Web+上提供数据库账号及密码。在代购场景下，如果RDS实例上没有此账号，Web+将会自动为您创建该账号；在导入已有RDS场景下，您需要自己保证该RDS实例上存在相应的账号，并正确设置账号权限。

## 使用CLI配置RDS {#section_eby_eh7_hsr .section}

CLI配置RDS需要通过Wpfile文件来进行，您可以通过wpctl dump命令来获取部署环境的Wpfile文件。您可以增加、修改或删除RDS的配置项，然后通过apply命令使其生效。

Wpfile文件中RDS配置项归类在resources.rds下，配置项含义为：

|配置项|有效值|默认值|描述|
|---|---|---|--|
|enable|true / false|false|是否启用RDS|
|imported|true / false|false|是否使用已有RDS|
|rdsId|有效的RDS实例ID|无|RDS实例ID。在导入已有RDS场景下，需要提供此配置项来指明导入的RDS。|
|zoneId|有效的RDS可用区ID|无|RDS可用区ID。可通过RDS的DescribeRegions接口来获取有效的RDS可用区。|
|VSwitches|交换机ID|无|指定RDS所在可用区的交换机。|
|engine|数据库类型，取值：MySQL ；SQLServer ；PostgreSQL ；PPAS ；MariaDB 。|无|数据库类型|
|engineVersion|数据库版本，取值： -   MySQL：5.5/5.6/5.7/8.0
-   SQL Server：2008r2/2012/2012\_ent\_ha/2012\_std\_ha/2012\_web/2016\_ent\_ha/2016\_std\_ha/2016\_web/2017\_ent
-   PostgreSQL：9.4/10.0
-   PPAS：9.3/10.0
-   MariaDB：10.3

 |无|数据库版本|
|storageType|实例存储类型，取值： -   local\_ssd/ephemeral\_ssd：本地SSD盘（推荐）
-   cloud\_ssd：SSD云盘
-   cloud\_essd：ESSD云盘

 |无|存储类型|
|storageSize|整数|100|存储大小，单位G|
|dbInstanceClass|有效的实例规格|无|实例规格，有效值详见 实例规格表 。|
|databaseName|字符串|webplus|数据库名|
|characterSetName|字符集，取值： -   MySQL/MariaDB实例：utf8、gbk、latin1、utf8mb4
-   SQL Server实例：Chinese\_PRC\_CI\_AS、Chinese\_PRC\_CS\_AS、SQL\_Latin1\_General\_CP1\_CI\_AS、SQL\_Latin1\_General\_CP1\_CS\_AS、Chinese\_PRC\_BIN

 | -   MySQL/MariaDB实例：utf8mb4
-   SQL Server实例：Chinese\_PRC\_CI\_AS

 |字符集|
|accountName|字符串|webplus|数据库账号|
|accountPassword|字符串|无|数据库账号密码|
|category|实例系列，取值： -   Basic：基础版
-   HighAvailability：高可用版
-   AlwaysOn：集群版
-   Finance：金融版（仅中国站支持）

 |无|数据库实例系列|

## 在应用进程中使用RDS {#section_fgq_mks_c34 .section}

当启用RDS后，在Web+通过环境变量方式来向您的应用程序提供数据库连接信息。您在应用进程中可通过如下环境变量来获取相应连接信息：

-   WP\_RDS\_ENGINE：数据库类型，例如MySQL。
-   WP\_RDS\_CONNECTION\_ADDRESS：数据库连接地址，例如rm-xxxx.mysql.rds.aliyuncs.com 。
-   WP\_RDS\_PORT：数据库连接端口，例如3306。
-   WP\_RDS\_ACCOUNT\_NAME：数据库账号名。
-   WP\_RDS\_ACCOUNT\_PASSWORD：数据库密码。
-   WP\_RDS\_DATABASE：数据库名。

