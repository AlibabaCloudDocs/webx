# 初始化CLI {#concept_187781 .concept}

在使用CLI前需要进行全局配置和检查：包括使用`wpctl configure`设置账号AK、SK、语言等全局信息和使用`wpctl doctor`校验此账号权限等，以及使用`wpctl init`初始化当前工作目录下的默认地域、应用和环境等信息。

## 步骤一：配置全局信息 {#section_l48_p9p_rm5 .section}

使用`wpctl configure`设置AK、SK和语言等全局信息。

方法1：执行命令并创建一个名叫test的profile。（Region ID信息请参见[表 1](../../../../cn.zh-CN/产品简介/支持地域.md#table_7hc_s2a_iq1)。）

``` {#codeblock_ash_t52_reu}
$ wpctl configure --profile test
Configuring profile 'test' in '' authenticate mode...
Access Key Id []: yourAk
Access Key Secret []: yourSk
Default Region Id []: cn-shenzhen                              
Default Output Format [json]: json (Only support json))
Default Language [zh|en] en: en

Saving profile[test] ...Done.
Configure Done!!!
$ wpctl configure list
Profile   | Credential         | Valid   | Region           | Language
--------- | ------------------ | ------- | ---------------- | --------
test *    | AK:***rAk          | Valid   | cn-shenzhen      | en
```

方法2：使用一条完整配置命令进行配置。

``` {#codeblock_e5a_0om_6m4}
$ wpctl configure -p test1 --access-key-id yourAk --access-key-secret yourSk --region cn-shenzhen --language en
Configuring profile 'test1' in '' authenticate mode...
Saving profile[test1] ...Done.
Configure Done!!!
$ wpctl configure list
Profile   | Credential         | Valid   | Region           | Language
--------- | ------------------ | ------- | ---------------- | --------
default   | AK:***zGQ          | Valid   | cn-shenzhen      | en
test1 *   | AK:***zGQ          | Valid   | cn-shenzhen      | en
```

方法3：使用环境变量配置，环境变量罗列如下。

``` {#codeblock_c3r_abt_vgl}
ALICLOUD_ACCESS_KEY
ALICLOUD_SECRET_KEY
ALICLOUD_REGION
```

切换profile并修改地域等参数。

``` {#codeblock_k7j_ow0_vb0}
$ webxctl configure set --profile default --region cn-hangzhou
$ webxctl configure list
Profile   | Credential         | Valid   | Region           | Language
--------- | ------------------ | ------- | ---------------- | --------
default * | AK:***zGQ          | Valid   | cn-hangzhou      | en
jungle    | AK:***3M1          | Valid   | cn-shenzhen      | en
test      | AK:***rAk          | Valid   | cn-shenzhen      | en
```

## 步骤二：校验账号权限 {#section_3zx_hko_hux .section}

使用`wpctl doctor`命令可对当前账号的权限等进行校检。首先校检是否开通Web+业务，然后校检是否开通关联产品，最后校检Web+是否完成需要角色的授权，校检通过才可以使用其他功能。

``` {#codeblock_jvo_f4k_kyq}
$ wpctl doctor
[OK] Describe aliyun authority (1s)
[Products related checked]
+----+------+------------------------+--------------------------------+--------+
| NO | NAME |         TITLE          |              DESC              | STATUS |
+----+------+------------------------+--------------------------------+--------+
|  1 | ESS  | Auto Scaling           | Elastic scaling (Auto ...      | OK     |
|  2 | OSS  | Object Storage Service | Massive, secure, ...           | OK     |
+----+------+------------------------+--------------------------------+--------+
[OK] Describe role status (1s)
[Role related checked]
+----+---------+---------------------------------+------------+
| NO | SERVICE |              ROLE               | AUTHORIZED |
+----+---------+---------------------------------+------------+
|  1 | WebPlus | AliyunWebPlusDefaultRole        | true       |
|  2 | ECS     | AliyunECSInstanceForWebPlusRole | true       |
+----+---------+---------------------------------+------------+
[doctor check ok, have fun]
```

## 步骤三：选择应用和环境 {#section_bym_f0j_8js .section}

使用`wpctl init`初始化当前工作目录。

选择的地域没有应用时会要求创建一个新的应用。同时在CLI中所有的交互都将显示为绿色，您一般只需要选择序号或者按提示输入即可。

``` {#codeblock_lmu_jr2_mot}
$ wpctl init
1) cn-hangzhou
2) cn-shenzhen
Select a default region, default region is [2:cn-shenzhen]: 1                          
No application get
0) new a application
Select a default application, default is create a application [0:new a application]:0
You are going to create a application, please enter application name: demo-test
...
[OK] Create application demo-test
No environment to select
...
[wpctl init successed]
```

当选择的地域已有应用时, 选择默认环境后将保存初始化的结果到工作目录`.webplus`中。

``` {#codeblock_c1q_o3r_f1q}
$ webxctl init
...
0) new a application
1) demo-test2
2) demo-test1
Select a default application, default Application name [1:demo-test2]: 1
...
1) demo-test-env
Select a default environment, default environment [demo-test-env]: 1
Saving config to webxconfig:[/Users/***/Documents/webp/webp-cli-demo/.webplus/wpconfig.yaml
```

