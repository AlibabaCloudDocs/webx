# CLI命令 {#concept_187020 .concept}

Web+命令行界面（wpctl）使您可以直接从终端轻松创建和管理Web+，下面罗列了Web+的核心CLI命令解释说明。您还可以使用`wpctl --help`、`wpctl help`或`wpctl h`在终端中查看所有的CLI命令。

## 应用相关 {#section_9u3_mtk_8go .section}

查询应用

查询本账号下的应用的列表。

``` {#codeblock_e5x_qqm_xoo}
USAGE:
  wpctl app:list

EXAMPLES：
  wpctl app:list
```

切换应用

查询应用后切换到目标应用。

``` {#codeblock_g29_5xh_mhv}
USAGE:
  wpctl app:use ID/Name

EXAMPLES：
  wpctl app:use app-demo
```

|参数|Flag|
|--|----|
|应用ID或应用Name|无|

删除应用

删除应用需要释放应用下的所有环境。

``` {#codeblock_xj4_mng_c91}
USAGE:
  wpctl app:delete ID/Name

EXAMPLES：
  wpctl app:delete app-demo
```

|参数|Flag|
|--|----|
|应用ID或应用Name|无|

## 环境相关 {#section_12g_ic7_z2m .section}

apply命令

`apply`命令可以创建应用、创建环境和更新环境，`apply --help`命令可以自动获取工作目录的数据。

``` {#codeblock_yjv_hsr_5jh}
USAGE:
    wpctl env:apply [Wpfile] [*.zip] [flags]

FLAGS:
  --package-id  set the package id
  --package,-p  set the package url
  --label,-l    set the label of package
  --template,-t set the template id(only) to apply
  --type        set the default env type, 'HighAvailability' [HA] or 'StandAlone' [SA]
  --app,-a      set the application
  --env,-e      set the env
  --category    set the category of the new application('Tomcat', or 'Java')
  --stack-id    set the stackId of the new application
  --quiet,-q    run quietly
  --json,-j     result return as json
  --create-on-absent,-C create application or environment on absent，combine with --app/env flags
  --help        print help
`wpctl apply
  --app target_app (--create-on-absent to create when it doesn't exist)
  --env target_env (--create-on-absent to create when it doesn't exist)
  --package https://*** --label v1 (or just using existed package with --pkgId)`
`wpctl apply --template template***
  --app app_template_belongs_to
  --env new_env_name --create-on-absent
```

apply可不接参数，也可使用Wpfile类文件作为参数，也可使用zip包作为参数。

|Flags|说明|
|-----|--|
|--package-id|设置复用的包版本。|
|--package或-p|设置部署包。|
|--label或-l|设置包标识。|
|--template或-t|设置部署的模板ID。|
|--type|设置使用的配置类型: -   高可用：HighAvailability或HA。
-   低成本：LowCost或LC。

 |
|--app或-a|设置应用。|
|--env或-e|设置环境。|
|--category|设置新建应用的平台类型：Tomcat或Java。|
|--stack-id|设置新建应用的技术栈ID： -   Java 8 / Aliyun Linux 2.1903：ws-6c937c98a9c0296d0c4823984
-   Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903：ws-6c937c98a9c0296d0c4823983

 |
|--quiet或-q|静默执行命令，不会输出过程信息和返回信息，如需要信息输出请使用`--json`。|
|--json或-j|以json字串格式输出结果信息|
|--create-on-absent或-C|与`--app`或`--env`结合使用，用于在指定的app或者env不存在时创建应用或环境。|

初始化环境

初始化环境的工作目录，包括区域，默认应用，默认环境。

``` {#codeblock_hlb_dre_ngf}
USAGE:
  wpctl init
```

查看环境列表

查看当前应用下的环境列表。

``` {#codeblock_93p_mnl_6lv}
USAGE:
  wpctl env:list  [flags]

FLAGS:
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:list --app appName
```

切换环境

查看当前应用下的环境列表。

``` {#codeblock_f5o_fs1_2sq}
USAGE:
  wpctl env:use id/name

FLAGS:
  --app,-a set the application
  --help   print help
```

|参数|Flag|
|--|----|
|应用ID或应用Name|--app或-a：指定目的环境的所属应用， 支持ID和Name。|

显示环境信息

``` {#codeblock_fhu_nhp_d78}
USAGE:
  wpctl env:info  [flags]

FLAGS:
  --env,-e set the env
  --app,-a set the application
  --json,-j result return as json
  --help   print help

EXAMPLES：
  wpctl env:info --env envName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。
-   --json或-j：输出json字串格式的信息。

 |

启动环境

``` {#codeblock_yri_g32_w27}
USAGE:
  wpctl env:start  [flags]

FLAGS:
  --app,-a set the application
  --env,-e set the env
  --help   print help

EXAMPLES：
  wpctl env:start --env envId/name
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

停止环境

``` {#codeblock_reu_iyd_pey}
USAGE:
  wpctl env:stop  [flags]

FLAGS:
  --app,-a set the application
  --env,-e set the env
  --help   print help

EXAMPLES：
  wpctl env:stop --env envId/name
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

释放环境

``` {#codeblock_p00_sns_87z}
USAGE:
  wpctl env:terminate [flags]

FLAGS:
  --app,-a   set the application
  --env,-e   set the env
  --help     print help

EXAMPLES：
  wbnx env:terminate
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

扩缩环境

``` {#codeblock_2oc_r5a_ez1}
USAGE:
  wpctl env:scale instanceNum [flags]

FLAGS:
  --app,-a set the application
  --env,-e set the env
  --help   print help

EXAMPLES：
  wbnx env:scale 1
```

|参数|Flag|
|--|----|
|指定扩缩目标实例数，可指定范围为0-100。| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

删除环境

``` {#codeblock_r1m_z6h_p6i}
USAGE:
  wpctl env:delete ID/Name [flags]

FLAGS:
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:delete env-demo
```

|参数|Flag|
|--|----|
|指定要删除的环境ID或Name|-app或-a：可以指定环境所属的应用，支持ID和Name。|

生成环境模板

``` {#codeblock_2p3_53d_9qt}
USAGE:
  wpctl env:save [flags]

FLAGS:
  --name,-n set the name
  --app,-a  set the application
  --env,-e  set the env
  --help    print help

EXAMPLES：
  wpctl env:save --name templateName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。
-   --name或-n：可以指定保存成的模板的名称。

 |

下载环境

``` {#codeblock_5sn_n3b_oru}
USAGE:
  wpctl env:dump [flags]

FLAGS:
  --env,-e set the env
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:dump --env envName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

检查环境健康

``` {#codeblock_54s_11g_dmy}
USAGE:
  wpctl env:health  [flags]

FLAGS:
  --env,-e set the env
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:health --env envName --app appName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

监控环境

``` {#codeblock_bav_ob6_541}
USAGE:
  wpctl env:top  [flags]

FLAGS:
  --env,-e set the env
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:top --env envName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

查看环境事件

``` {#codeblock_31o_6s9_ta2}
USAGE:
  wpctl env:events  [flags]

FLAGS:
  --env,-e    set the env
  --app,-a    set the application
  --change,-c set the changeId
  --help      print help

EXAMPLES：
  wpctl env:events --env envName
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。
-   --change或-c：可以指定查看某次变更的事件，需要changeId

 |

更新环境部署包

``` {#codeblock_e4s_xcz_opw}
USAGE:
  wpctl env:deploy package [flags]

FLAGS:
  --label,-l set the label of package
  --app,-a   set the application
  --env,-e   set the env
  --help     print help

EXAMPLES：
  wpctl env:deploy *.war --label v2
```

|参数|Flag|
|--|----|
|指定更新使用的部署包。| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。
-   --label或-l：可以指定包上传的名称。

 |

访问环境

``` {#codeblock_826_bed_12b}
USAGE:
  wpctl env:open [flags]

FLAGS:
  --app,-a set the application
  --env,-e set the env
  --help   print help

EXAMPLES：
  wpctl env:open --env envId/name
```

|参数|Flag|
|--|----|
|无| -   -env或-e：指定打印信息的环境，支持ID和Name。
-   -app或-a：可以指定环境所属的应用，支持ID和Name。

 |

## 实例操作相关 {#section_yny_4yk_u74 .section}

登录实例

通过SSH登录环境下的实例。

``` {#codeblock_wp8_e10_1a5}
USAGE:
  wpctl env:ssh envName/ID [flags]

FLAGS:
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl env:ssh envName/ID --app appName/ID
```

|参数|Flag|
|--|----|
|指定要登录的环境ID或Name。|-app或-a：可以指定环境所属的应用，支持ID和Name。|

在环境实例上执行命令

``` {#codeblock_h61_zvm_cw8}
USAGE:
  wpctl env:exec <selector> <shell_command>[flags]
  :selector - `envName/id`
  The command will be execute by `root`

FLAGS:
  --quiet,-q   run quietly
  --timeout,-t execution timeout (in seconds, max is 86400)
  --json,-j    output as json (result will be base64 encoded)
  --force,-f   force to run command on all available servers
  --help       print help

EXAMPLES：
  wpctl env:exec envName 'echo hello'
```

## 模板相关 {#section_5ap_n4v_klv .section}

展示模板

``` {#codeblock_110_x5y_74i}
USAGE:
  wpctl template:list [flags]

FLAGS:
  --app,-a set the application
  --help   print hel

EXAMPLES：
  wpctl template:list
```

|参数|Flag|
|--|----|
|无|-app或-a：可以指定环境所属的应用，支持ID和Name。|

删除模板

``` {#codeblock_rv2_sgg_rxy}
USAGE:
  wpctl template:delete id/name [flags]

FLAGS:
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl template:delete templateName/ID
```

|参数|Flag|
|--|----|
|指定模板ID或Name|-app或-a：可以指定环境所属的应用，支持ID和Name。|

启动模板

``` {#codeblock_f1c_5gp_uoi}
USAGE:
  wpctl template:launch

FLAGS:
  --app,-a set the application
  --env,-e set the env
  --create-on-absent,-C create application or environment on absent，combine with --app/env flags
  --help   print help

EXAMPLES：
  wpctl template:launch templateName/id
```

|参数|Flag|
|--|----|
|指定模板ID或Name| -   --env或-e：可以指定模板拉起环境的名称。
-   --app/-a：可以指定模板所属应用，支持ID和Name。
-   --create-on-absent或-C：与--app或--env结合使用，用于在app或者env指定的对象不存在的情况下创建他们。

 |

## 其他命令 {#section_mfo_k19_84r .section}

展示部署包列表

``` {#codeblock_pjo_d0l_yy8}
USAGE:
  wpctl pkg:list [flags]

FLAGS:
  --app,-a set the application
  --help   print help

EXAMPLES：
  wpctl pkg:list --app appName
```

|参数|Flag|
|--|----|
|无|--app/-a：可以指定模板所属应用，支持ID和Name。|

配置账号

``` {#codeblock_n0c_qdv_1jf}
USAGE:
  wpctl configure --mode <AuthenticateMode> --profile <profileName>

COMMANDS:
  set    set config in non interactive mode
  list   list all config profile
  delete delete config profile

FLAGS:
   --language          use `--language [en|zh]` to assign language
  --region            use `--region <regionId>` to assign region
  --access-key-id     use `--access-key-id <AccessKeyId>` to assign AccessKeyId, required in AK/StsToken/RamRoleArn mode
  --access-key-secret use `--access-key-secret <AccessKeySecret>` to assign AccessKeySecret
  --help        print help
```

自动补全命令

脚本安装时，当前终端会自动补全，但是切换了shell 的tab则失效。

``` {#codeblock_wvm_6mt_49o}
USAGE:
  wpctl auto-completion [flags]

FLAGS:
  --uninstall uninstall auto completion
  --help      print help
```

|参数|Flag|
|--|----|
|无|--uninstall：卸载自动补全|

查看CLI版本

``` {#codeblock_bh5_ppw_3hq}
USAGE:
  wpctl version

EXAMPLE:
  wpctl version
```

更新CLI版本

``` {#codeblock_c4j_87q_w58}
USAGE:
  wpctl upgrade

EXAMPLE:
  wpctl upgrade
```

收集CLI信息

``` {#codeblock_ynv_64x_0pk}
USAGE:
  wpctl collect [flags]

FLAGS:
  --all  collect all log
  --help print help

EXAMPLE:
  wpctl collect
```

|参数|Flag|
|--|----|
|无|--all：收集日志信息时收集全部的日志信息|

检测产品开通、依赖和授权服务

``` {#codeblock_az0_qqs_jm7}
USAGE:
  wpctl doctor

EXAMPLE:
  wpctl doctor
```

## 问题反馈 {#section_yw4_8xv_a8y .section}

如果您在使用Web+过程中有任何疑问，欢迎您扫描下面的二维码加入钉钉群进行反馈。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/161244/156048103148830_zh-CN.jpg)

