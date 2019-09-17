# 通过Jenkins模板搭建部署环境 {#concept_268598 .concept}

Web+支持基于应用配置模版搭建专属环境。在应用配置模版中，可以预先自定义应用用到的资源、网络环境、程序路径等基本信息。本教程将以在CLI中使用Jenkins模板搭建部署环境为例，描述如何通过应用模版搭建一个可运行的环境。

## 前提条件 {#section_sv4_jwo_gv3 .section}

-   [开通Web+服务](../../../../cn.zh-CN/准备工作/开通相关服务并授权.md#section_e7m_lmj_c0l)

## 步骤一：下载并安装命令行工具 {#section_zl9_xdl_zf9 .section}

在Linux或macOS两个操作系统内，执行以下命令下载并安装CLI。

``` {#codeblock_wxa_erf_p2w}
eval "$(curl -s -L https://webplus-cn-shenzhen.oss-cn-shenzhen.aliyuncs.com/cli/install.sh)"
```

## 步骤二：配置命令行工具 {#section_l2u_jed_ib1 .section}

执行以下命令，使用您的注册账号的AccessKey ID和AccessKey Secret来完成CLI的注册配置，选择环境所在地域，创建一个例如叫demo的文件夹。

``` {#codeblock_qzn_unf_aqv}
wpctl configure --access-key-id "$ALICLOUD_ACCESS_KEY" --access-key-secret "$ALICLOUD_SECRET_KEY" --region "$ALICLOUD_REGION"  --profile demo
```

**说明：** ALICLOUD\_REGION可填写的参数值参见[Web+目前支持的地域](../DNICMS19100634/ZH-CN_TP_381811_V2.dita#concept_473790/table_7hc_s2a_iq1)的Region ID列。

## 步骤三：下载Jenkins启动模版 {#section_9km_i3y_0en .section}

Wpfile内保存了创建或更新环境的配置信息。Web+创建了一份Jenkins环境的模板，您可以通过执行以下命令下载模版，并将模板保存到Wpfile文件中。

``` {#codeblock_5l5_5gv_w6c}
wget http://aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/course/Jenkins5Wpfile -O Wpfile
```

**说明：** 使用Jenkins的启动模版，Web+将使用按量付费的方式，在默认的VPC与VSwitch下购买一台规格为ecs.g5.large（2 vCPU 8 GiB）的ECS实例，并安装AliyunLinux系统，然后将[Jenkins.war](http://mirrors.jenkins.io/war-stable/latest/jenkins.war)文件部署至购买的ECS实例上。

## 步骤四：基于Jenkins模版创建部署环境 {#section_5tv_32p_scr .section}

执行以下命令创建一个Web+的应用和部署环境。执行以下命令后，Web+将自动读取Wpfile内配置模板内容，基于Jenkins模板去创建环境。

``` {#codeblock_ig2_nsm_p0s}
wpctl env:apply --app WebPlusJenkins --env WebPlusJenkinsDemoEnv --create-on-absent
```

**说明：** 该部署操作首次执行时会耗时较久，请耐心等待约5分钟至环境创建完成。

## 步骤五：访问部署环境 {#section_zde_qnw_75v .section}

当应用和环境创建完成后，Web+将为您代购模板中的配置资源，需等待约2分钟至资源购买完成。您可使用以下命令访问部署环境。

1.  执行以下命令切换至创建的应用和部署环境。

    ``` {#codeblock_w63_tfh_ck8}
    wpctl env:use WebPlusJenkinsDemoEnv --app WebPlusJenkins
    ```

2.  执行以下命令查看事件列表。

    ``` {#codeblock_jkj_9lh_lfw}
    wpctl env:events
    ```

3.  执行以下命令查看环境信息并获取应用链接。

    ``` {#codeblock_p71_0ib_64f}
    wpctl env:info
    ```


## 步骤六：安装Jenkins模板环境 {#section_jn3_om9_1ku .section}

使用浏览器打开上面步骤配置的部署环境之后，您将开始安装Jenkins模板的环境，在安装的过程中，Jenkins会提示输入管理员密码，该密码可从文件`/home/admin/.jenkins/secrets/initialAdminPassword`从获取，您可在CLI中执行以下命令查看密码。

``` {#codeblock_4iy_0z6_dwu}
wpctl env:exec WebPlusJenkinsDemoEnv "cat /home/admin/.jenkins/secrets/initialAdminPassword"
```

## 更多信息 {#section_9yz_ag5_st4 .section}

-   使用控制台部署应用请参见：[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   CLI相关的更多命令请参见：[CLI命令](../DNICMS19100639/ZH-CN_TP_161078_V1.dita)。

## 问题反馈 {#section_q0u_syk_fgl .section}

如果您在使用Web+过程中有任何疑问，欢迎您扫描下面的二维码加入钉钉群进行反馈。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221972/156324924648828_zh-CN.jpg)

