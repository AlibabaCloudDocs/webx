# 使用Django开发应用 {#concept_1780772 .concept}

Django是Python的一个开放源代码的Web应用框架。本文档将演示如何使用Django创建一个应用和给应用添加MySQL数据库，并将其部署到Web+上。

## 步骤一：安装Django {#section_25o_kkt_i5o .section}

执行以下命令安装Django。由于在本文档中将使用MySQL，因此需要安装pymysql模块。

``` {#codeblock_ml6_bz9_nfz}
pip install Django pymysql 
```

**说明：** 使用Django（2.2版本以上）需要Python 3.5以上版本，在本文档将使用3.7.4版本作为示例。

## 步骤二：创建应用 {#section_ahd_iu7_hjk .section}

1.  执行以下命令执行django-admin命令来快速创建一个项目。

    ``` {#codeblock_sby_6kw_tym}
    django-admin startproject webplusdemo
    ```

2.  可以看到创建的目录结构如下。

    ``` {#codeblock_kxy_pg0_mos}
    webplusdemo/
    ├── manage.py
    └── webplusdemo
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
    ```

3.  执行以下命令执行django-admin命令来快速创建一个项目。

    ``` {#codeblock_tue_faf_a32}
    django-admin startproject webplusdemo
    ```


## 步骤三：打包应用 {#section_sis_3st_xfq .section}

1.  执行以下命令来修改settings.py中ALLOWED\_HOSTS配置项，允许所有域名的访问。

    ``` {#codeblock_kn4_jjw_1up}
    ALLOWED_HOSTS = ['*']
    ```

2.  执行以下命令改写settings.py中的数据库配置。Django默认使用sqlite数据库，本示例中将使用RDS中的MySQL数据库。

    ``` {#codeblock_h54_r3x_24e}
    # Database
    # https://docs.djangoproject.com/en/2.2/ref/settings/#databases
    
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.mysql',
            'NAME': os.environ['WP_RDS_DATABASE'],
            'USER': os.environ['WP_RDS_ACCOUNT_NAME'],
            'PASSWORD': os.environ['WP_RDS_ACCOUNT_PASSWORD'],
            'HOST': os.environ['WP_RDS_CONNECTION_ADDRESS'],
            'PORT': os.environ['WP_RDS_PORT'],
        }
    }
    ```

3.  进入webplusdemo目录，执行以下命令完成应用打包，生成部署包文件webplusdemo.zip。

    ``` {#codeblock_09o_wyt_mvy}
    zip -r webplusdemo.zip ./
    ```


## 步骤四：部署应用至Web+ {#section_zty_zwi_h0o .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为**Python**，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156629099055338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplusdemo.zip，设置部署包版本后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156629099155348_zh-CN.png)

5.  在**配置**页面选择**预设配置**为**自定义**模式。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161337/156629099155813_zh-CN.png)

6.  展开**云数据库RDS**，按图所示配置云数据库类型为**MySQL**，并选择数据库版本、系列和类型等数据库基本信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161337/156629099255815_zh-CN.png)

7.  展开**生命周期挂钩**，在**PostPrepareApp**编辑框内输入以下内容。配置完成后单击**完成创建**。

    ``` {#codeblock_711_3sd_slx}
    source /etc/bashrc && cd $APP_HOME && python manage.py migrate
    ```

8.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156629099255358_zh-CN.png)

    上面步骤配置了数据库，因此可以访问登录页。您可以通过在数据库写入用户表或执行`python manage.py createsupersuer`的方式来创建用户。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1410553/156629099256384_zh-CN.png)


## 更多信息 {#section_36l_kam_h1f .section}

-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   想了解更多Django信息，请进入[Django官方网站](https://docs.djangoproject.com/)或[Django Github项目](https://github.com/django)查看。

