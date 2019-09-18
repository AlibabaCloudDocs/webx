# 向Node.js应用部署环境中添加RDS数据库实例 {#concept_2261355 .concept}

您可以添加RDS数据库实例来存储应用中需持久保存的数据。本文在[将Express应用部署到Web+](ZH-CN_TP_1782212.dita#concept_2246021/section_ryv_773_osl)的基础上，展示如何为Node.js应用添加数据库并读写其中的数据。

## 环境变量 {#section_989_c6z_pni .section}

Web+会将数据库连接的相关信息存放在环境变量中，以便应用进行读取，相关环境变量请参考下表。

|变量名|变量值|变量说明|
|---|---|----|
|WP\_RDS\_ENGINE|MySQL|RDS数据库引擎|
|WP\_RDS\_CONNECTION\_ADDRESS|rm-\*\*\*.mysql.rds.aliyuncs.com|RDS内网连接地址|
|WP\_RDS\_PORT|3306|RDS端口号|
|WP\_RDS\_ACCOUNT\_NAME|webplus|RDS数据库账号名称|
|WP\_RDS\_ACCOUNT\_PASSWORD|自定义|RDS账号密码|
|WP\_RDS\_DATABASE|webplus|RDS数据库|

## 添加数据库驱动 {#section_dyn_gvm_7xm .section}

进入应用的项目工程目录，例如进入[将Express应用部署到Web+](ZH-CN_TP_1782212.dita#concept_2246021/section_ryv_773_osl)应用的webplus-express-app目录，执行以下命令添加MySQL数据库驱动。

``` {#codeblock_m5x_xmn_qzf}
npm install mysql
```

## 添加数据库访问功能 {#section_bcz_cyh_xlt .section}

打开routes/users.js文件，修改如下：

``` {#codeblock_gpx_87x_9pg}
var express = require('express');
var mysql = require('mysql');

var router = express.Router();

router.get('/', function(req, res, next) {
  var connection = mysql.createConnection({
    host: process.env.WP_RDS_CONNECTION_ADDRESS,
    user: process.env.WP_RDS_ACCOUNT_NAME,
    password: process.env.WP_RDS_ACCOUNT_PASSWORD,
    database: process.env.WP_RDS_DATABASE
  });

  connection.connect();

  connection.query('SELECT "Tom" AS user_name', function(error, results) {
    if (error) {
      throw error;
    }
    res.send('User name queried from database: ' + results[0].user_name);
  });
});

module.exports = router;
```

## 更多信息 { .section}

-   关于如何使用Web+来管理RDS，可参考[云数据库RDS](../DNICMS19100636/ZH-CN_TP_881838.dita)。

