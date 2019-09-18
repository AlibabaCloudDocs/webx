# 将Express应用部署到Web+ {#concept_2246021 .concept}

Express是一个快速开发Node.js应用的Web框架，可以用来快速开发API、Web、后端服务等各种应用。本文档介绍了如何开发一个简单的Express应用，并将其部署至Web+。

## 前提条件 {#section_6vw_dvc_kiv .section}

已配置好了Node.js的开发环境，相关操作请参见[设置Node.js开发环境](ZH-CN_TP_1781944.dita)。

## 步骤一：安装express-generator {#section_7uj_gt3_40j .section}

本文将使用express-generator来快速生成Express项目。请执行以下命令安装express-generator。

``` {#codeblock_orz_eni_4m1}
npm install -g express-generator
```

**说明：** 如果您安装了Node.js 8.2.0及以上版本，可跳过此步在创建应用时直接使用npx命令运行express-generator。

## 步骤二：创建应用 {#section_ryv_773_osl .section}

执行以下命令创建名为webplus-express-app的应用。

``` {#codeblock_mgm_c3i_u6j}
express webplus-express-app
```

**说明：** 如果您安装了Node.js 8.2.0及以上版本，可执行`npx express-generator webplus-express-app`命令直接运行express-generator而无需安装。

执行上述命令会创建一个名为webplus-express-app的目录，结构如下：

``` {#codeblock_onf_cge_i1s}
webplus-express-app/
├── app.js
├── bin
│   └── www
├── package.json
├── public
│   ├── images
│   ├── javascripts
│   └── stylesheets
│       └── style.css
├── routes
│   ├── index.js
│   └── users.js
└── views
    ├── error.jade
    ├── index.jade
    └── layout.jade
```

## 步骤三：安装本地依赖 {#section_kt5_7f8_32v .section}

1.  执行以下命令进入创建好的应用目录。

    ``` {#codeblock_t6w_h8k_6co}
    cd webplus-express-app
    ```

2.  执行以下命令安装本地依赖。

    ``` {#codeblock_50r_g5b_lz1}
    npm install
    ```


## 步骤四：在本地运行应用 {#section_306_u1i_6je .section}

1.  执行以下命令在本地运行应用，以验证其是否可以正常工作。

    ``` {#codeblock_bqs_b09_o9p}
    npm start
    ```

    当您看到命令行页面上显示以下信息时，则表示应用启动成功。

    ``` {#codeblock_nud_ofd_kz5}
    > webplus-express-app@0.0.0 start /home/admin/webplus-express-app
    > node ./bin/www
    ```

2.  查看运行结果：
    -   在浏览器中输入http://localhost:3000来访问应用。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1782212/156877817060945_zh-CN.png)

    -   执行curl http://localhost:3000命令，查看返回的运行结果：

        ``` {#codeblock_eym_05i_xde}
        <!DOCTYPE html>
        <html>
            <head>
                <title>Express</title>
                <link rel="stylesheet" href="/stylesheets/style.css">
            </head>
            <body>
                <h1>Express</h1>
                <p>Welcome to Express</p>
            </body>
        </html>
        ```

        **说明：** 为方便查看，此处对返回的信息进行了格式化，原始结果是一整行文本。

3.  查看应用的运行结果之后，可以使用CTRL+C停止服务。

## 步骤五：打包应用 {#section_3b1_hu5_uym .section}

执行以下命令将上面生成的应用的项目工程打包。

``` {#codeblock_bkj_dsl_jcw}
zip -r webplus-express-app.zip .
```

**说明：** 生成的部署包需包含node\_modules目录，且压缩包不能包含第一级目录，打包示例如下：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1782212/156877817060957_zh-CN.png)

## 步骤六：将应用部署至Web+ {#section_l7v_c8o_3sp .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为Node.js，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1782212/156877817060960_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplus-express-app.zip，设置部署包版本后单击**完成创建**。
5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1782212/156877817060966_zh-CN.png)


## 更多信息 {#section_pyx_lxh_rp7 .section}

-   在Web+控制台快速部署应用的视频演示请参见[在Web+控制台创建应用和部署环境](../DNWEBX19101931/ZH-CN_TP_519470_V3.dita)。
-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   完成应用托管之后的应用的管理操作请参见[应用详情概览](../DNICMS19100635/ZH-CN_TP_163214_V1.dita)。
-   管理应用所在的部署环境的操作请参见[部署环境概览](../DNICMS19100636/ZH-CN_TP_163212_V1.dita)。

