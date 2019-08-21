# 设置Java开发环境 {#concept_189186 .concept}

在本地开发环境测试Java应用，需准备好相关的开发环境。本文将介绍Java开发环境的设置步骤，并提供相关工具的安装链接。

## 安装Java开发工具包 {#section_ydv_ihj_h5w .section}

选择您的开发平台，参考以下方式安装JDK。

Linux 

1.  在[Oracle官网](https://www.oracle.com/technetwork/java/javase/downloads/index.html)下载二进制安装包，例如jdk-8uversion-linux-x64.tar.gz。
2.  进入JDK安装包所在目录。
3.  执行以下命令解压安装包：

    ``` {#codeblock_4c5_oe2_hx3}
    tar zxvf jdk-8uversion-linux-x64.tar.gz
    ```

4.  按以下方式配置环境变量。
    1.  执行以下命令打开配置文件。

        ``` {#codeblock_bdv_1ht_jz9}
        vim ~/.bashrc
        ```

    2.  在配置文件中添加以下内容。

        ``` {#codeblock_cgc_8fy_jjl}
        JAVA_HOME=/Java安装路径
        CLASSPATH=$JAVA_HOME/lib/
        PATH=$PATH:$JAVA_HOME/bin
        export PATH JAVA_HOME CLASSPATH
        ```

    3.  执行以下命令使配置生效。

        ``` {#codeblock_fki_9sg_1km}
        source ~/.bashrc
        ```

    4.  检查是否安装成功。

        ``` {#codeblock_qwq_ef9_i7i}
        java -version
        javac -version
        ```


Mac

1.  在[Oracle官网](https://www.oracle.com/technetwork/java/javase/downloads/index.html)下载安装包，例如jdk-8uversion-macosx-x64.dmg。
2.  进入JDK安装包所在目录，双击安装包按照提示指令进行安装。
3.  按以下方式配置环境变量。
    1.  执行以下命令打开配置文件。

        ``` {#codeblock_om6_gf4_ftw}
        vim ~/.bashrc
        ```

    2.  在配置文件中添加以下内容。

        ``` {#codeblock_dfi_jup_isq}
        JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_151.jdk/Contents/Home
        CLASSPAHT=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
        PATH=$JAVA_HOME/bin:$PATH:
        export JAVA_HOME
        export CLASSPATH
        export PATH
        ```

    3.  执行以下命令使配置生效。

        ``` {#codeblock_2hp_389_tpv}
        source ~/.bashrc
        ```

    4.  检查是否安装成功。

        ``` {#codeblock_pv2_52l_m2f}
        java -version
        javac -version
        ```


Windows

1.  在[Oracle官网](https://www.oracle.com/technetwork/java/javase/downloads/index.html)下载安装包，例如jdk-8version-windows-x64.exe。
2.  进入JDK安装包所在目录，双击安装包按照提示指令进行安装。
3.  按以下方式配置环境变量。
    1.  设置JAVA\_HOME环境变量。

        ``` {#codeblock_m90_1ay_4zt}
        C:\Program Files\Java\jdk1.8.0
        ```

    2.  修改环境变量PATH，在PATH变量后添加如下内容

        ``` {#codeblock_u1u_g40_ns7}
        {系统中原PATH环境变量};%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin
        ```

    3.  添加CLASSPATH环境变量。

        ``` {#codeblock_x3n_roe_qgg}
        %JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
        ```

    4.  检查是否安装成功。

        ``` {#codeblock_9cn_jn7_q7n}
        java -version
        ```


## 安装Tomcat {#section_cuu_3ir_ipi .section}

访问[Apache Tomcat](https://tomcat.apache.org/whichversion.html)，根据**Apache Tomcat Versions**的说明下载合适的Tomcat版本。

## 安装IDE {#section_j8d_ebd_dz6 .section}

集成开发环境（IDE）是用于提供程序开发环境的应用程序，一般包括代码编辑器、编译器、调试器和图形用户界面等工具。如果您还没使用IDE进行过Java开发，请根据个人开发习惯下载安装Eclipse或IntelliJ IDEA，下载链接如下：

-   [Eclipse](https://www.eclipse.org/downloads/)
-   [IntelliJ IDEA](https://www.jetbrains.com/idea/)

