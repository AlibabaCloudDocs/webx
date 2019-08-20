# 使用Flask开发应用 {#concept_1780642 .concept}

Flask是Python的一个轻量级Web应用框架。本文档将演示如何使用Flask创建一个应用，并将其部署到Web+上。

## 步骤一：创建应用 {#section_5bo_czx_86j .section}

1.  按照以下目录结构创建一个名为weplusdemo的目录，并在该目录下创建一个名为application.py的文件。

    ``` {#codeblock_ejc_chs_e0y}
    webplusdemo
    └── application.py
    ```

2.  在application.py文件中输入以下内容。

    ``` {#codeblock_jdm_xn2_08a}
    from flask import Flask
    app = Flask(__name__)
    
    @app.route('/')
    def hello_world():
        return 'Hello World!'
    ```

    **说明：** 

    -   Web+会自动识别名为application.py的文件和全局变量APP，若您需要使用其他文件名，需要通过Procfile或启动命令来指定需要的启动命令，具体操作请参见[使用Procfile配置应用进程](ZH-CN_TP_163221.dita)和[命令与生命周期挂钩](../DNICMS19100636/ZH-CN_TP_1253418.dita)。
    -   Web+默认会使用gunicorn作为Flask应用的服务器。

## 步骤二：打包应用 {#section_c2i_hao_dyx .section}

进入webplusdemo目录，执行以下命令完成应用打包，生成部署包文件webplusdemo.zip。

``` {#codeblock_dmo_7qx_ydl}
zip -r webplusdemo.zip ./
```

## 步骤三：部署应用至Web+ {#section_y3v_dso_tq8 .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为**Python**，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156629097455338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplusdemo.zip，设置部署包版本后单击**完成创建**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156629097455348_zh-CN.png)

5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1410538/156629097456385_zh-CN.png)


## 更多信息 {#section_xsv_6mv_2m8 .section}

-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   想了解更多Flask信息，请进入[Flask官方网站](https://palletsprojects.com/p/flask/)查看。

