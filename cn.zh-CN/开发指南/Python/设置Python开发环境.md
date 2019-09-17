# 设置Python开发环境 {#concept_1732320 .concept}

在本地开发环境测试Python应用，需准备好相关的开发环境。本文将介绍Python开发环境的设置步骤，并提供相关工具的安装页面链接。

## 安装Python {#section_z09_qh1_pc4 .section}

根据您的开发平台，从[Python官网](https://www.python.org/downloads/)下载安装包。

**说明：** 为了和Web+的技术栈版本更好兼容，建议您下载[Python 3.7.4](https://www.python.org/downloads/release/python-374/)或[Python 2.7.16](https://www.python.org/downloads/release/python-2716/)。

Linux 

1.  进入Python安装包（例如Python-3.7.4.tgz）所在目录，执行以下命令解压安装包。

    ``` {#codeblock_74m_kav_zft}
    tar xvf Python-3.7.4.tgz
    ```

2.  进入Python安装包所在目录，执行以下命令进行编译和安装。

    ``` {#codeblock_p27_83r_m2w}
    ./configure --with-ensurepip=install
    make && make install
    ```


macOS

执行以下命令来使用brew来快速安装Python。

``` {#codeblock_unu_lhc_lbh}
brew update && brew install python
```

Windows

进入Python安装包所在目录，双击安装包按照提示指令进行安装。

## 虚拟环境 {#section_jt3_bj7_7hb .section}

当同时开发多个项目时，使用Python虚拟环境来隔离这些项目是比较好的实践，这可以让您避免项目之间的依赖包的版本可能冲突的问题。

虚拟环境的具体用法请参见[虚拟环境和包](https://docs.python.org/zh-cn/3/tutorial/venv.html)。

## 使用IDE {#section_jmm_ew6_pg2 .section}

使用集成开发环境 \(IDE\) 提供了便于应用程序开发的大量功能，可以显著提高开发效率，以下是常见于Python开发中使用的IDE：

-   [Eclipse](https://www.eclipse.org/)
-   [PyCharm（商业软件）](https://www.jetbrains.com/pycharm/)

