# 使用Procfile配置应用进程 {#concept_189192 .concept}

通常情况下，Web+对于每种技术栈类型设置了默认的启动命令，您也可以通过配置启动命令或者使用Procfile来指定，Web+将优先使用Procfile中的启动命令。

## Procfile {#section_x7t_zpo_0yh .section}

如果需要使用Procfile，请在源包根目录中包含一个名为Procfile的文件，格式如下：

``` {#codeblock_6ma_is3_n0i}
web: <command>
```

**说明：** 

-   Procfile中的每行内容都必须符合以下正则表达式：^\[A-Za-z0-9\_\]+:\\s\*.+$。
-   Web+将识别开头为web:的命令，并以此作为服务的启动命令。
-   此命令必须一直在前台运行，命令执行结束时服务即停止。
-   启动命令的工作目录为应用部署包的根目录。
-   启动命令将以admin用户身份执行。

