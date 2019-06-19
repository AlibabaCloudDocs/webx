# 快速部署Java应用（CLI） {#concept_268597 .concept}

本教程将以在CLI中使用Web+提供的Java样例程序为例，展示使用程序部署包进行应用的创建和部署的过程。

## 步骤一：下载并安装命令行工具 {#section_fmp_kz6_0ug .section}

在Linux与Mac两个系统内，执行以下命令下载并安装CLI。

``` {#codeblock_4mr_88r_jco}
eval "$(curl -s -L https://webplus-cn-shenzhen.oss-cn-shenzhen.aliyuncs.com/cli/install.sh)"
```

## 步骤二：配置命令行工具 {#section_4rn_jj5_yxx .section}

执行以下命令：使用您的注册账号的AccessKey ID和AccessKey Secret来完成CLI的注册配置，选择环境所在地域（Region），创建一个例如叫demo的文件夹。

``` {#codeblock_w12_1n4_pmr}
wpctl configure --access-key-id "$ALICLOUD_ACCESS_KEY" --access-key-secret "$ALICLOUD_SECRET_KEY" --region "$ALICLOUD_REGION"  --profile demo 
```

**说明：** Web+现支持的地域有华北2（北京）、华北3（张家口）、华东1（杭州）、华东2（上海）和华南1（深圳）。

## 步骤三：克隆Java样例程序 {#section_p0d_pas_bzb .section}

执行以下命令，克隆Web+提供的样例程序到工程根目录中。

如果您有自己的Java程序，将下面的命令中的地址路径换成您自己样例程序所在的路径即可。

``` {#codeblock_j8t_ikd_18o}
git clone https://github.com/aliyun/alibabacloud-webplus-demo-java.git && cd alibabacloud-webplus-demo-java
```

## 步骤四：编译程序包并创建应用 {#section_op7_l2e_urm .section}

1.  克隆完样例程序后，执行以下命令来打包样例程序。

    ``` {#codeblock_rt1_eag_h6u}
    mvn package
    ```

2.  执行以下命令，上传样例程序并创建应用和部署环境。

    ``` {#codeblock_20t_mpn_9jg}
    wpctl env:apply --package target/webplus-demo-java*.jar --label webplusVersion0.1 --category Java --env webplusEnvDemo --app webplusAppDemo --create-on-absent
    ```

    **说明：** 在这一步中，指定了对应的应用名称与部署环境名称。--create-on-absent用以标明如果不存在此应用或者环境时，将新建一个应用或环境。


## 步骤五：访问应用 {#section_2fh_od8_5jv .section}

当应用和环境创建完成后，Web+将为您代购模板中的配置资源，需等待约2分钟至资源购完成。您可执行如下操作来访问应用。

1.  执行以下命令切换至创建的应用和部署环境。

    ``` {#codeblock_q45_6bd_usm}
    wpctl env:use webplusEnvDemo --app webplusAppDemo
    ```

2.  执行以下命令查看事件列表，确认已完成变更。

    ``` {#codeblock_ke7_55x_pjs}
    wpctl env:events
    ```

3.  执行以下命令查看环境信息并获取应用链接。

    ``` {#codeblock_dpb_82c_3g0}
    wpctl env:info
    ```

4.  打开获取到的链接并访问应用首页。

## 步骤六：释放部署环境 {#section_hz1_wfz_p3b .section}

执行以下命令可以释放部署环境。

默认情况下，当释放部署环境后，Web+将为您代购的ECS实例将被释放并终止计费，新建的SLB实例当前没有其他正在监听的流量和后端机器时也将被释放从而终止计费。

``` {#codeblock_pcl_337_mip}
wpctl env:terminate --app webplusAppDemo --env webplusEnvDemo
```

**说明：** Web+生成的部署环境的资源的付费模式都是按量付费，如果您想在环境释放后保留ECS实例，您可以登录[ECS控制台](https://ecs.console.aliyun.com)，将创建的ECS实例转成包年包月的计费模式。

## 更多信息 {#section_ygl_z7c_x0i .section}

-   CLI相关的更多命令可参阅文档[CLI命令](../DNICMS19100639/ZH-CN_TP_161078_V1.dita)。
-   使用控制台快速部署应用可参阅文档[快速部署Tomcat应用（控制台）](ZH-CN_TP_217610_V2.dita)。

## 问题反馈 {#section_u9e_48v_un5 .section}

如果您在使用Web+过程中有任何疑问，欢迎您扫描下面的二维码加入钉钉群进行反馈。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221972/156048111248828_zh-CN.jpg)

