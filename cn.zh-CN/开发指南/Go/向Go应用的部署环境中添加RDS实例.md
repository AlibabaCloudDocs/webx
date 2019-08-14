# 向Go应用的部署环境中添加RDS实例 {#concept_189191 .concept}

您可以使用阿里云云数据库RDS的数据库实例来存储应用中需持久保存的数据。本文将介绍如何为Go应用添加数据库并验证应用与数据库是否连接。

## 环境变量 {#section_1y2_gjl_awn .section}

Web+会将数据库连接的相关信息存放在环境变量中，以便应用进行读取，相关环境变量请参考下表。

|变量名|变量值|变量说明|
|---|---|----|
|WP\_RDS\_ENGINE|MySQL|RDS数据库引擎|
|WP\_RDS\_CONNECTION\_ADDRESS|rm-\*\*\*.mysql.rds.aliyuncs.com|RDS内网连接地址|
|WP\_RDS\_PORT|3306|RDS端口号|
|WP\_RDS\_ACCOUNT\_NAME|webplus|RDS数据库账号名称|
|WP\_RDS\_ACCOUNT\_PASSWORD|\*\*\*\*\*|RDS账号密码|
|WP\_RDS\_DATABASE|webplus|RDS数据库|

## 安装数据库驱动 {#section_zrr_msj_eig .section}

执行以下命令，安装MySQL数据库驱动：

``` {#codeblock_qpo_wdq_n2w}
go get github.com/go-sql-driver/mysql
```

## 添加数据库 {#section_zwv_nf9_qg1 .section}

添加数据库的操作请参照以下样例代码进行配置。

``` {#codeblock_hdx_e1p_5az}
package main

import (
  &quot;database/sql&quot;
  &quot;fmt&quot;
  _ &quot;github.com/go-sql-driver/mysql&quot;
  &quot;os&quot;
)

func main() {
  user := os.Getenv(&quot;WP_RDS_ACCOUNT_NAME&quot;)
  passwd := os.Getenv(&quot;WP_RDS_ACCOUNT_PASSWORD&quot;)
  host := os.Getenv(&quot;WP_RDS_CONNECTION_ADDRESS&quot;)
  port := os.Getenv(&quot;WP_RDS_PORT&quot;)

  connStr := fmt.Sprintf(&quot;%s:%s@tcp(%s:%s)/?timeout=30s&quot;, user, passwd, host, port)
  db, _ := sql.Open(&quot;mysql&quot;, connStr)
  defer db.Close()

  sqlTxt := &quot;select 'OK' as result&quot;
  rows, _ := db.Query(sqlTxt)
  var result string

  for rows.Next(){
    _ = rows.Scan(&amp;result)
  }

  // output &quot;OK&quot;
  fmt.Println(result)
}
```

## 更多信息 {#section_6ua_szs_bg6 .section}

-   关于如何使用Web+来管理RDS，可参考[云数据库RDS](../DNICMS19100636/ZH-CN_TP_881838.dita)。

