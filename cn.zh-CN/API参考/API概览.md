# API概览 {#doc_1135443 .concept}

Web应用托管服务提供以下相关API接口。

## 应用 {#section_gxz_56t_yw5 .section}

|API|描述|
|---|--|
|[CreateApplication](cn.zh-CN/API参考/应用/CreateApplication.md)|使用CreateApplication创建一个新应用。|
|[DeleteApplication](cn.zh-CN/API参考/应用/DeleteApplication.md)|调用DeleteApplication删除一个应用。|
|[DescribeApplications](cn.zh-CN/API参考/应用/DescribeApplications.md)|调用DescribeApplications查询应用信息。|
|[UpdateApplication](cn.zh-CN/API参考/应用/UpdateApplication.md)|调用UpdateApplication更新应用。|

## 存储 {#section_x7l_mp4_idx .section}

|API|描述|
|---|--|
|[CreateStorage](cn.zh-CN/API参考/存储/CreateStorage.md)|调用CreateStorage创建一个存储桶。|
|[DescribeStorage](cn.zh-CN/API参考/存储/DescribeStorage.md)|调用DescribeStorage查询存储。|

## 技术栈 {#section_iln_zkx_ayc .section}

|API|描述|
|---|--|
|[DescribeCategories](cn.zh-CN/API参考/技术栈/DescribeCategories.md)|调用DescribeCategories查询平台类型。|
|[DescribeStacks](cn.zh-CN/API参考/技术栈/DescribeStacks.md)|调用DescribeStacks查询技术栈。|

## 部署包版本 {#section_blk_rta_0mp .section}

|API|描述|
|---|--|
|[DeletePkgVersion](cn.zh-CN/API参考/部署包版本/DeletePkgVersion.md)|调用DeletePkgVersion删除一个部署包版本。|
|[DescribePkgVersions](cn.zh-CN/API参考/部署包版本/DescribePkgVersions.md)|调用DescribePkgVersions查询部署包版本。|
|[CreatePkgVersion](cn.zh-CN/API参考/部署包版本/CreatePkgVersion.md)|调用CreatePkgVersion创建一个部署包版本。|

## 部署环境 {#section_mbr_vv6_aj5 .section}

|API|描述|
|---|--|
|[CreateAppEnv](cn.zh-CN/API参考/部署环境/CreateAppEnv.md)|调用CreateAppEnv创建一个部署环境。|
|[DeleteAppEnv](cn.zh-CN/API参考/部署环境/DeleteAppEnv.md)|调用DeleteAppEnv删除一个环境。|
|[DescribeAppEnvStatus](cn.zh-CN/API参考/部署环境/DescribeAppEnvStatus.md)|调用DescribeAppEnvStatus查询给定环境的状态。|
|[DescribeAppEnvs](cn.zh-CN/API参考/部署环境/DescribeAppEnvs.md)|调用DescribeAppEnvs查询符合条件的部署环境。|
|[UpdateAppEnv](cn.zh-CN/API参考/部署环境/UpdateAppEnv.md)|调用此API更新一个部署环境。|
|[TerminateAppEnv](cn.zh-CN/API参考/部署环境/TerminateAppEnv.md)|调用TerminateAppEnv来终止一个环境。|
|[StopAppEnv](cn.zh-CN/API参考/部署环境/StopAppEnv.md)|调用StopAppEnv停止一个部署环境。|
|[DescribeAppEnvInstanceHealth](cn.zh-CN/API参考/部署环境/DescribeAppEnvInstanceHealth.md)|调用DescribeAppEnvInstanceHealth查询一个环境内所有ECS实例的健康状态。|
|[StartAppEnv](cn.zh-CN/API参考/部署环境/StartAppEnv.md)|调用StartAppEnv启动一个部署环境。|
|[RestartAppEnv](cn.zh-CN/API参考/部署环境/RestartAppEnv.md)|调用RestartAppEnv重启一个部署环境。|
|[DescribeInstanceHealth](cn.zh-CN/API参考/部署环境/DescribeInstanceHealth.md)|调用DescribeInstanceHealth查询一个给定ECS实例的健康状态。|
|[RebuildAppEnv](cn.zh-CN/API参考/部署环境/RebuildAppEnv.md)|调用RebuildAppEnv重建一个部署环境。|
|[GatherAppEnvLog](cn.zh-CN/API参考/部署环境/GatherAppEnvLog.md)|调用GatherAppEnvLog来收集一个部署环境中指定实例的日志信息。|
|[GatherAppEnvStats](cn.zh-CN/API参考/部署环境/GatherAppEnvStats.md)|调用GatherAppEnvStats来收集一个部署环境中的诊断信息。|
|[DescribeEnvResource](cn.zh-CN/API参考/部署环境/DescribeEnvResource.md)|调用DescribeEnvResource查询一个环境内的所有资源。|
|[DescribeGatherLogResult](cn.zh-CN/API参考/部署环境/DescribeGatherLogResult.md)|调用DescribeGatherLogResult查询一个收集日志的变更信息。|
|[DescribeGatherStatsResult](cn.zh-CN/API参考/部署环境/DescribeGatherStatsResult.md)|调用DescribeGatherStatsResult查询一个收集诊断的变更信息。|

## 配置模板 {#section_gtw_9jj_8ye .section}

|API|描述|
|---|--|
|[CreateConfigTemplate](cn.zh-CN/API参考/配置模板/CreateConfigTemplate.md)|调用CreateConfigTemplate从一个原有环境来创建一个配置模板。|
|[DeleteConfigTemplate](cn.zh-CN/API参考/配置模板/DeleteConfigTemplate.md)|调用DeleteConfigTemplate删除一个配置模板。|
|[DescribeConfigTemplates](cn.zh-CN/API参考/配置模板/DescribeConfigTemplates.md)|调用DescribeConfigTemplates查询配置模板。|
|[UpdateConfigTemplate](cn.zh-CN/API参考/配置模板/UpdateConfigTemplate.md)|调用UpdateConfigTemplate来更新配置模板。|

## 配置 {#section_kla_ykd_jv2 .section}

|API|描述|
|---|--|
|[DescribeConfigSettings](cn.zh-CN/API参考/配置/DescribeConfigSettings.md)|调用DescribeConfigSettings查询配置设置。|
|[DescribeConfigOptions](cn.zh-CN/API参考/配置/DescribeConfigOptions.md)|调用DescribeConfigOptions查询配置选项信息。|
|[DescribeConfigIndex](cn.zh-CN/API参考/配置/DescribeConfigIndex.md)|调用DescribeConfigIndex查询配置索引。|
|[ValidateConfigSetting](cn.zh-CN/API参考/配置/ValidateConfigSetting.md)|调用ValidateConfigSetting来验证一个配置的设置有效性。|

## 变更 {#section_bof_xic_ksy .section}

|API|描述|
|---|--|
|[AbortChange](cn.zh-CN/API参考/变更/AbortChange.md)|使用AbortChange可以中止一次变更。|
|[DeleteChange](cn.zh-CN/API参考/变更/DeleteChange.md)|调用DeleteChange删除一个变更。|
|[ResumeChange](cn.zh-CN/API参考/变更/ResumeChange.md)|调用ResumeChange来恢复一个被暂停的变更操作。|
|[PauseChange](cn.zh-CN/API参考/变更/PauseChange.md)|调用PauseChange来暂停一个未完成的变更操作。|
|[DescribeChange](cn.zh-CN/API参考/变更/DescribeChange.md)|调用DescribeChanges查询给定环境内所有变更信息或给定变更ID的变更信息。|
|[DescribeChanges](cn.zh-CN/API参考/变更/DescribeChanges.md)|调用DescribeChanges查询所有变更信息或给定环境内所有变更信息。|

## 事件 {#section_zvt_tjb_rga .section}

|API|描述|
|---|--|
|[DescribeEvents](cn.zh-CN/API参考/事件/DescribeEvents.md)|调用DescribeEvents查询事件。|

