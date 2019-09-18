# 设置Go开发环境 {#concept_189190 .concept}

在本地开发环境测试Go应用，需准备好相关的开发环境。本文将介绍Go开发环境的设置步骤，并提供相关工具的安装页面链接。

## 安装Go {#section_iux_jq9_d5p .section}

根据您的开发平台，从[Go官方网站](https://golang.org/dl/)下载对应的版本，对于各个主流平台，Go都有很完善的支持，下载完成后请分别参考以下方式安装。

Linux

1.  使用以下命令将安装包解压到/usr/local/go目录下：

    ``` {#codeblock_p60_59u_n5c}
    tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz
    ```

2.  解压后将可执行文件目录配置到PATH环境变量，将以下命令添加到/etc/profile或$HOME/.profile。

    ``` {#codeblock_8o9_fpf_mp7}
    export PATH=$PATH:/usr/local/go/bin
    ```

3.  执行以下命令使环境变量立即生效。

    ``` {#codeblock_lor_plf_1ve}
    source $HOME/.profile
    ```


macOS

执行以下命令使用brew来快速安装Go。

``` {#codeblock_j3f_yy4_yqm}
brew update && brew install go
```

Windows

进入Go安装包所在目录，运行下载的.msi文件即可安装，无需其他配置。

## 配置GOPATH {#section_26t_d5e_236 .section}

环境变量GOPATH标识了工作区的目录，通常情况下您需要设定此环境变量来指定工作区目录。各个平台对应设置方法请参见文档[Setting GOPATH](https://github.com/golang/go/wiki/SettingGOPATH)。

## 安装IDE {#section_85f_uky_w6o .section}

集成开发环境（IDE，Integrated Development Environment ）是用于提供应用开发环境的应用程序，一般包括代码编辑器、编译器、调试器和图形用户界面等工具，可以显著提高开发效率。以下是Go开发中常用的IDE，但下列IDE可能需要通过安装插件来支持Go开发。

-   [Eclipse](https://www.eclipse.org/)
-   [Visual Studio Code](https://code.visualstudio.com/)
-   [GoLand（商业软件）](https://www.jetbrains.com/go/)

