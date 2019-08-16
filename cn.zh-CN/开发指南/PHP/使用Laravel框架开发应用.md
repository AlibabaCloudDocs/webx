# 使用Laravel框架开发应用 {#concept_187794 .concept}

Laravel是一套简洁、优雅的PHP Web开发框架。本文档将演示如何使用Laravel创建一个应用和添加MySQL数据库，并将其部署到Web+上。

## 前提条件 {#section_v1u_0bq_zol .section}

-   [设置PHP开发环境](ZH-CN_TP_161335.dita)。

    **说明：** 使用Laravel框架开发应用需要PHP 5.5.9或更高版本。


## 步骤一：创建应用 {#section_ue7_0z2_5eo .section}

1.  执行以下命令使用Composer工具来创建一个名为webplusdemo的项目，该过程可能需要几分钟。

    ``` {#codeblock_yz0_gk4_zc0}
    composer create-project --prefer-dist laravel/laravel webplusdemo
    ```

2.  执行以下命令使用PHP内置的开发服务器来运行此项目。

    ``` {#codeblock_vw1_i5u_eqm}
    php artisan serve
    ```

3.  打开浏览器输入下图地址访问应用。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161337/156594564055802_zh-CN.png)


## 步骤二：打包应用 {#section_ns6_d34_w4i .section}

1.  进入项目目录，执行以下命令来激活Laravel内置的用户权限管理功能。

    ``` {#codeblock_x1x_9ib_m0j}
    php artisan make:auth
    ```

2.  修改.env文件中数据库相关的配置，使其关联Web+的相关环境变量。

    ``` {#codeblock_f3j_hvc_tvk}
    DB_CONNECTION=mysql
    DB_HOST=${WP_RDS_CONNECTION_ADDRESS}
    DB_PORT=${WP_RDS_PORT}
    DB_DATABASE=${WP_RDS_DATABASE}
    DB_USERNAME=${WP_RDS_ACCOUNT_NAME}
    DB_PASSWORD=${WP_RDS_ACCOUNT_PASSWORD}
    ```

3.  执行以下命令，安装所有的依赖。

    ``` {#codeblock_ckd_mfn_3fo}
    composer install
    ```

4.  使用zip命令打包项目下所有的内容生成压缩包webplusdemo.zip。

    ``` {#codeblock_p57_r7z_g5c}
    zip -r webplusdemo.zip ./
    ```


## 步骤三：部署应用至Web+ {#section_pmr_y04_p4h .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为PHP，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156594564055338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplusdemo.zip，设置部署包版本后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156594564055348_zh-CN.png)

5.  在**配置**页面选择**预设配置**为**自定义**模式。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161337/156594564155813_zh-CN.png)

6.  展开**云数据库RDS**，按图所示配置云数据库类型为**MySQL**，并选择数据库版本、系列和类型等数据库基本信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161337/156594564155815_zh-CN.png)

7.  展开**生命周期挂钩**，在**PostPrepareApp**编辑框内输入以下内容。

    ``` {#codeblock_dpu_0wo_onp}
    cd $APP_HOME && /usr/local/php/bin/php artisan migrate 
    ```

8.  在配置页面最下方单击**完成创建**。
9.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156594564255358_zh-CN.png)


## 更多信息 {#section_mw5_dqv_0mn .section}

-   关于如何使用Web+来管理RDS，可参考[云数据库RDS](../DNICMS19100636/ZH-CN_TP_881838.dita)。
-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。

