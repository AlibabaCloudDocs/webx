# 使用Symfony开发应用 {#concept_187793 .concept}

Symfony是一个基于MVC模式的面向对象的PHP框架，本文档将演示如何使用Symfony创建一个应用，并将其部署到Web+上。

## 前提条件 {#section_ss7_w2a_qm3 .section}

-   [设置PHP开发环境](ZH-CN_TP_161335.dita)。

    **说明：** Symfony 3需要PHP 5.5.9或更高版本，以及PHP的intl 扩展。


## 步骤一：安装Symfony {#section_x70_7pf_npg .section}

1.  执行以下命令安装Symfony CLI。

    ``` {#codeblock_8sg_rlv_4sx}
    curl -sS https://get.symfony.com/cli/installer | bash
    ```

2.  将CLI的可执行文件移动到系统命令目录下。

    ``` {#codeblock_9mi_v8r_7mf}
    mv ~/.symfony/bin/symfony /usr/local/bin/symfony
    ```


## 步骤二：创建应用 {#section_49g_8za_pid .section}

1.  执行以下命令使用CLI工具快速创建一个Symfony演示项目。

    ``` {#codeblock_lvc_xjn_tw3}
    symfony new --demo webplusdemo
    ```

    创建过程需要几分钟，创建完成后将生成名为webplusdemo的项目。

2.  进入项目目录执行以下命令安装依赖。

    ``` {#codeblock_ttp_sw5_luq}
    composer install
    ```

3.  执行以下命令，使用CLI工具附带的开发服务器启动服务。

    ``` {#codeblock_8qn_uyt_c4h}
    symfony server:start
    ```

4.  打开浏览器访问http://localhost:8000，进入Symfony示例应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161336/156620783955860_zh-CN.png)


## 步骤三：打包应用 {#section_ees_gc3_e72 .section}

1.  Web+支持您使用Nginx或Apache来作为Web服务器，若您希望使用Apache，可通过在项目目录下执行以下命令生成.htaccess文件，如果使用Nginx，则可跳过此步骤。

    ``` {#codeblock_dr6_e10_ttz}
    composer require symfony/apache-pack
    ```

2.  执行以下命令完成应用打包，生成部署包文件webplusdemo.zip。

    ``` {#codeblock_c7r_x4j_mli}
    zip -r webplusdemo.zip ./
    ```


## 步骤四：部署应用至Web+ {#section_0zn_bea_zk7 .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为PHP，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156620784055338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplusdemo.zip，设置部署包版本后单击**完成创建**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156620784055348_zh-CN.png)

5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156620784055358_zh-CN.png)


## 更多信息 {#section_cfh_0ec_nqr .section}

-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   想了解更多Symfony信息，请进入[Symfony官方网站](https://symfony.com/)查看。

