# 设置Node.js开发环境 {#concept_2245584 .concept}

在本地开发环境测试Node.js应用，需要准备相关的开发环境。本文将介绍Node.js开发环境的设置步骤，并提供相关工具的安装页面链接。

## 安装Node.js {#section_x0x_6dh_nyt .section}

在[Node.js官方网站](https://nodejs.org/)下载安装包。

**说明：** 为了和Web+的技术栈版本更好兼容，建议您下载[Node.js 10.16.0](https://nodejs.org/download/release/v10.16.0/)[Node.js 8.16.0](https://nodejs.org/download/release/v8.16.0/)

Linux

1.  进入Node.js安装包（例如node-v10.16.3-linux-x64.tar.xz）所在目录，执行以下命令将安装包解压到/usr/local目录下。

    ``` {#codeblock_d3o_0u2_eb6}
    sudo tar -C /usr/local -xzf node-v10.16.3-linux-x64.tar.xz
    ```

2.  执行以下命令创建软链接/usr/local/node指向刚解压的安装包路径。

    ``` {#codeblock_7kr_3il_v00}
    sudo ln -s /usr/local/node-v10.16.3-linux-x64 /usr/local/node
    ```

3.  解压后将可执行文件目录配置到Path环境变量，将以下命令添加到$HOME/.profile。

    ``` {#codeblock_mbh_lb0_1a9}
    export PATH=$PATH:/usr/local/node/bin
    ```

4.  执行以下命令使环境变量立即生效。

    ``` {#codeblock_sqy_jvl_xzr}
    source $HOME/.profile
    ```

5.  使用以下命令验证Node.js是否安装成功。

    ``` {#codeblock_9g2_5gd_gnp}
    node --version && npm --version
    ```

    如果显示如下信息，则说明安装包已成功安装。

    ``` {#codeblock_9h8_yf8_37t}
    v10.16.0
    6.9.0
    ```


macOS

执行以下命令使用brew来快速安装Node.js。

``` {#codeblock_pos_cih_o94}
brew update && brew install node
```

Windows

进入Node.js安装包所在目录，运行下载的.msi文件即可安装，无需其他配置。

## 安装IDE {#section_k97_qjw_kd1 .section}

集成开发环境（IDE，Integrated Development Environment ）是用于提供应用开发环境的应用程序，一般包括代码编辑器、编译器、调试器和图形用户界面等工具，可以显著提高开发效率。以下是Node.js开发中常用的IDE，但下列IDE可能需要通过安装插件来支持Node.js开发。

-   [Visual Studio Code](https://code.visualstudio.com/)
-   [Atom](https://atom.io/)
-   [WebStorm（商业软件）](https://www.jetbrains.com/webstorm/)

