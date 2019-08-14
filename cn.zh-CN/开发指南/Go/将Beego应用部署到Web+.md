# 将Beego应用部署到Web+ {#concept_189182 .concept}

Beego是一个快速开发Go应用的HTTP框架，可以用来快速开发API、Web、后端服务等各种应用。本文档介绍了如何开发一个简单的Beego应用，并将其部署至Web+。

## 步骤一：安装Beego {#section_5tw_01x_337 .section}

1.  执行以下命令来安装Beego和工具bee。

    ``` {#codeblock_h9k_r8m_wtw}
    go get -u github.com/astaxie/beego
    go get -u github.com/beego/bee
    ```

2.  执行以下命令将$GOPATH/bin目录加入$PATH环境变量。

    ``` {#codeblock_h4o_k25_2qx}
    echo 'export PATH="$GOPATH/bin:$PATH"' >> ~/.profile
    source >> ~/.profile
    ```


## 步骤二：创建应用 {#section_xio_mp5_5sx .section}

1.  打开终端，进入$GOPATH/src所在的目录，执行以下命令来快速创建一个命名为webplusdemo的项目。

    ``` {#codeblock_v8g_y0c_r87}
    bee new webplusdemo
    ```

    上述命令会创建一个名为webplusdemo的目录，结构如下：

    ``` {#codeblock_vcs_jsq_nn9}
    webplusdemo
    ├── conf
    │   └── app.conf
    ├── controllers
    │   └── default.go
    ├── main.go
    ├── models
    ├── routers
    │   └── router.go
    ├── static
    │   ├── css
    │   ├── img
    │   └── js
    │       └── reload.min.js
    ├── tests
    │   └── default_test.go
    └── views
       └── index.tpl
    ```

2.  进入项目目录，执行bee run。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163211/156578269255403_zh-CN.png)

3.  打开浏览器，输入http://localhost:8080来访问项目。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/163211/156578269255404_zh-CN.png)


## 步骤三：打包应用 {#section_y0g_uz0_k3p .section}

1.  在项目目录下新建Procfile来给Go应用指定启动命令，填写以下内容，并保存。

    ``` {#codeblock_tto_d7c_0vf}
    web: ./webplusdemo
    ```

2.  使用bee工具来对打包工程。

    ``` {#codeblock_8yl_pbr_vbu}
    bee pack -be GOOS=linux -be GOARCH=amd64 -f zip
    ```

    执行完上述命令，将会在项目目录下生成一个名为webplusdemo.zip的压缩包，按照下述步骤来将该Go应用部署至Web+。


## 步骤四：创建应用并完成部署 {#section_r6p_xy9_xw5 .section}

1.  登录 [Web+控制台](https://webplus.console.aliyun.com)，并在页面左上角选择所需地域。
2.  在**概览**页**最近更新的部署环境**区域的右上角单击**新建**。
3.  在**应用基本信息**页面选择**技术栈类型**为Java，设置应用基本信息，设置完成后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156578269355338_zh-CN.png)

4.  在**部署环境信息**页面设置**部署环境名称**，部署包来源选择**上传本地程序**，上传您刚打包的webplusdemo.zip，设置部署包版本后单击**完成创建**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156578269355348_zh-CN.png)

5.  在**完成创建**页面单击**查看该应用**或**完成创建**可进入**应用详情**页面。单击部署环境名称进入**部署环境详情**页面，然后单击**公网访问地址**右侧的链接进入应用首页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161338/156578269355358_zh-CN.png)


## 常见问题 {#section_jig_d2e_i4m .section}

健康检查失败导致网站无法访问怎么办？

如果使用SLB，请在健康检查URL的controller中接受head请求，否则可能会导致健康检查失败，网站无法访问。

``` {#codeblock_n1w_0uu_out}
package controllers

import (
  "github.com/astaxie/beego"
)

type MainController struct {
  beego.Controller
}

func (c *MainController) Get() {
  c.Data["Website"] = "beego.me"
  c.Data["Email"] = "astaxie@gmail.com"
  c.TplName = "index.tpl"
}


func (c *MainController) Head() {
  c.Ctx.Output.Body([]byte(""))
}
```

## 更多信息 {#section_u01_ctv_nty .section}

-   在控制台部署应用的详细配置步骤请参见[部署应用](../DNICMS19100635/ZH-CN_TP_159334_V1.dita)。
-   使用CLI完成应用创建和部署的操作请参见[在CLI快速部署应用](ZH-CN_TP_221972_V2.dita)。
-   完成应用托管之后的应用的管理操作请参见[应用详情概览](../DNICMS19100635/ZH-CN_TP_163214_V1.dita)。
-   管理应用所在的部署环境的操作请参见[部署环境概览](../DNICMS19100636/ZH-CN_TP_163212_V1.dita)。

