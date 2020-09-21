---
keyword: [Jenkins, ASP.NET Core, 部署, 持续集成, 命令行工具]
---

# 使用Jenkins部署ASP.NET Core应用

本文以ASP.NET Core应用为例，介绍了如何在Jenkins中使用Web+命令行工具部署应用。

## 背景信息

本文档中使用的是ASP.NET Core的[eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb)示例程序。该示例程序展示了电子书的一些原理和运行模式。

## 前提条件

-   [开通Web+相关服务并授权](/intl.zh-CN/准备工作/开通Web+相关服务并授权.md)
-   已安装Jenkins，详情请参见[在Web+控制台部署Jenkins](/intl.zh-CN/教程/在Web+控制台部署Jenkins.md)。

## 步骤一：环境准备

1.  安装Git。

    1.  以root身份登录运行Jenkins的ECS实例，执行以下命令：

        ```
        yum install -y git
        ```

        **说明：** 下文如无特别说明，均指以root身份在运行有Jenkins的服务器上执行命令。

    2.  安装完成以后，执行以下命令：

        ```
        which git
        ```

        记录以上命令的输出结果。

2.  执行以下命令安装.NET SDK。

    ```
    sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
    sudo yum install -y dotnet-sdk-3.1
    ```

3.  执行以下命令安装Entity Framework Core的命令行工具。

    ```
    dotnet tool install --global dotnet-ef
    ```

    安装完成后，按照提示退出当前会话后重新登录。

4.  执行以下命令安装Web+命令行工具。

    ```
    eval "$(curl -s -L https://webplus-cn-shenzhen.oss-cn-shenzhen.aliyuncs.com/cli/install.sh)"
    ```

5.  执行以下步骤配置Web+命令行工具。

    1.  以root身份登录运行Jenkins的ECS服务器，然后执行以下命令切换为admin用户。

        ```
        su - admin
        ```

    2.  执行以下命令，配置Web+命令行工具。

        ```
        wpctl configure --access-key-id <ACCESS_KEY_ID> --access-key-secret <ACCESS_KEY_SECRET> --region <REGION> --profile webplus
        ```

        **说明：**

        -   上述命令中ACCESS\_KEY\_ID和ACCESS\_KEY\_SECRET的获取方法，请参见[创建AccessKey]()。
        -   REGION参数是Web+部署应用所在的地域，Web+支持的地域请参见[支持地域](/intl.zh-CN/产品简介/支持地域.md)。

## 步骤二：使用Jenkins部署ASP.NET Core应用

1.  登录Jenkins。

2.  在**Jenkins**页面的左侧导航栏单击**Manage Jenkins**，然后在**Manage Jenkins**页面单击**Global Tool Configuration**。

    ![Global Tool Configuration页面。](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3210307951/p102105.png)

3.  在**Git**区域，在**Path to Git executable**文本框输入上面执行which git命令输出的结果，然后单击**Apply**。

    ![配置Git](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3210307951/p102106.png)

4.  在**Jenkins**主页面的左侧导航栏单击**New Item**以创建一个任务。

    ![new item](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4210307951/p102108.png)

5.  在**Enter an item name**文本框内输入任务名称，选择**Pipeline**，然后单击**OK**。

    ![CREATE A NEW ITEM](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4210307951/p102109.png)

6.  单击**Pipeline**页签。

    ![Pipeline](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4210307951/p102110.png)

7.  在Pipeline中输入以下命令脚本，然后单击**Save**。

    ```
    pipeline {
        agent any
    
        stages {
            stage('Prepare') {
                steps {
                    // Clean Jenkins workspace.
                    cleanWs()
                    // Clone eShopOnWeb repository.
                    git 'https://github.com/dotnet-architecture/eShopOnWeb'
                }
            }
    
            stage('Build') {
                steps {
                    // Build this project.
                    sh 'dotnet restore src/Web/Web.csproj'
                    sh 'dotnet tool restore --configfile src/Web/.config/dotnet-tool.json'
                    sh 'dotnet publish src/Web/Web.csproj -c Release -o out -r linux-x64 --self-contained'
                    // Tell Web+ how to start this application.
                    sh 'echo "Web: ASPNETCORE_ENVIRONMENT=Development ./Web" > out/Procfile'
                    // Package this project.
                    sh 'cd out && zip -qr webplus-dotnet-demo.zip .'
                }
            }
    
            stage('Deploy') {
                steps {
                    sh 'wpctl env:apply -y --package out/webplus-dotnet-demo.zip --category "ASP.NET Core" --app webplus-dotnet-demo --env test-env --create-on-absent'
                }
            }
        }
    }
    ```

8.  在左侧导航栏单击**Build Now**以启动流水线。

    ![build now](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4210307951/p102115.png)

9.  流水线部署完成后，参照以下步骤访问已部署的应用。

    1.  登录[Web+控制台](http://webplus-intl.console.aliyun.com/)，并在页面左上角选择地域。

    2.  在**最近更新的部署环境**区域右上角单击**查看全部**。

    3.  在**应用及部署环境**页面查找到目标应用，单击应用左侧的**+**图标展开应用所包含的部署环境列表。

    4.  单击部署环境ID进入部署环境的**概览**页面，单击**公网访问地址**右侧的地址链接，即可访问已部署的应用。

        ![查看地址链接](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4210307951/p102117.png)


**相关文档**  


[使用CLI部署Jenkins](/intl.zh-CN/教程/使用CLI部署Jenkins.md)

