# 设置PHP开发环境 {#concept_187792 .concept}

在本地开发环境测试PHP应用，需准备好相关的开发环境。本文将介绍PHP开发环境的设置步骤，并提供相关工具的安装页面链接。

## 安装PHP {#section_sgb_c40_7bx .section}

请根据以下操作安装PHP和一些常用扩展。如果您没有特别的要求，请获取最新版本。

Linux 

1.  在[PHP官网](https://www.php.net/downloads.php)下载安装包，例如php-7.3.8.tar.bz2 \(sig\)。
2.  进入安装包所在目录。
3.  执行以下命令安装包：

    ``` {#codeblock_zqt_bm0_dd2}
    $ sudo yum install php
    ```


macOS 

1.  在[PHP官网](https://www.php.net/downloads.php)下载安装包，例如php-7.3.8.tar.bz2 \(sig\)。
2.  执行以下命令安装包：

    ``` {#codeblock_ix4_6z6_izt}
    $ brew install php
    ```


Windows 

1.  在[PHP For Windows](https://windows.php.net/download)下载Windows系统安装包，例如PHP 7.3 \(7.3.8\)。
2.  进入PHP安装包所在目录，运行下载的文件即可安装，无需其他配置。

## 安装Composer {#section_fpo_y7l_f0q .section}

Composer 是用于PHP的依赖项管理器。您可以使用它来安装库、跟踪应用程序的依赖项并为热门PHP框架生成项目。

1.  使用来自getcomposer.org的PHP脚本安装Composer。

    ``` {#codeblock_p15_xfh_ata}
    $ curl -s https://getcomposer.org/installer | php
    ```

2.  安装程序将在当前目录中生成PHAR文件。将此文件移动到环境PATH中的位置以便将此文件用作可执行文件。

    ``` {#codeblock_rdt_y9g_jj5}
    $ mv composer.phar ~/.local/bin/composer
    ```

3.  使用require命令安装库。

    ``` {#codeblock_y4b_qi3_inf}
    $ composer require twig/twig
    ```


Composer 会将您在本地安装的库添加到您的项目[composer.json](https://docs.aws.amazon.com/zh_cn/elasticbeanstalk/latest/dg/php-configuration-composer.html)文件。在部署项目代码时，Web+将使用Composer在您的环境中的应用实例上安装此文件中列出的库。如果您在安装Composer时遇到问题，请访问[Composer官网](https://getcomposer.org)。

## 安装IDE {#section_u3r_8zt_2yj .section}

集成开发环境（IDE，Integrated Development Environment ）是用于提供应用开发环境的应用程序，一般包括代码编辑器、编译器、调试器和图形用户界面等工具，可以显著提高开发效率。以下是PHP开发中常用的IDE。

-   [Eclipse](https://www.eclipse.org/)
-   [PhpStorm](https://www.jetbrains.com/phpstorm/)

