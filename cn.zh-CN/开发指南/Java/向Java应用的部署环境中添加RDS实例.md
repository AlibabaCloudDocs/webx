# 向Java应用的部署环境中添加RDS实例 {#concept_187796 .concept}

您可以使用阿里云云数据库RDS的数据库实例来存储应用中需持久保存的数据。本文以给基于Spring Boot框架开发的Java应用添加RDS MySQL数据库为例，展示如何为Java应用添加数据库并验证应用与数据库是否连接。

## 环境变量 {#section_x78_dx5_fim .section}

Web+会将数据库连接的相关信息存放在环境变量中，以便应用进行读取，相关环境变量请参考下表。

|变量名|变量值|变量说明|
|---|---|----|
|WP\_RDS\_ENGINE|MySQL|RDS数据库引擎|
|WP\_RDS\_CONNECTION\_ADDRESS|rm-\*\*\*.mysql.rds.aliyuncs.com|RDS内网连接地址|
|WP\_RDS\_PORT|3306|RDS端口号|
|WP\_RDS\_ACCOUNT\_NAME|webplus|RDS数据库账号名称|
|WP\_RDS\_ACCOUNT\_PASSWORD|自定义|RDS账号密码|
|WP\_RDS\_DATABASE|webplus|RDS数据库|

## 添加依赖和修改配置文件 {#section_7tt_u6o_jsm .section}

1.  打开SpringBoot工程中的pom.xml文件，添加JDBC依赖和MySQL依赖。

    ``` {#codeblock_8h6_bhv_wy6}
    ​<!-- JDBC依赖 -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-jdbc</artifactId>
    </dependency>
    <!-- MySQL依赖 -->
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
    </dependency>
    ```

2.  打开工程中的application.properties配置文件，您可以按以下方式使用环境变量配置JDBC的连接参数，其中NONE可以修改为默认数值。

    ``` {#codeblock_00j_iae_shp}
    ​spring.datasource.driver-class-name=com.mysql.jdbc.Driver
    spring.datasource.url=jdbc:mysql://${WP_RDS_CONNECTION_ADDRESS:NONE}:${WP_RDS_PORT:3306}/rdsitem?useUnicode=true&characterEncoding=utf-8
    spring.datasource.username=${WP_RDS_ACCOUNT_NAME:NONE}
    spring.datasource.password=${WP_RDS_ACCOUNT_PASSWORD:NONE}​
    ```


## 连接数据库 {#section_dge_x66_04g .section}

修改依赖和配置后，启动应用时SpringBoot会根据配置文件自动连接数据库，下面的代码片段展示了如何在Web+中的应用访问数据库。

``` {#codeblock_omg_lkm_hbg}
​    @Autowired
    private JdbcTemplate jdbcTemplate;    
    // 从数据库item中查询
    public List<Item> fetchItems() {
        final String sql="select id,title,completed from item";
        RowMapper<Item> rowMapper=new BeanPropertyRowMapper<>(Item.class);
        return jdbcTemplate.query(sql, rowMapper);
    }​
```

其中，Item类定义如下：

``` {#codeblock_nle_nuf_tky}
​public class Item {
    private String id;
    private String title;
    private boolean completed;

    public String getId() {
        return id;
    }
    public void setId(String id) {
        this.id = id;
    }
    public String getTitle() {
        return title;
    }
    public void setTitle(String title) {
        this.title = title;
    }
    public boolean getCompleted() {
        return completed;
    }
    public void setCompleted(boolean completed) {
        this.completed = completed;
    }
    Item() {

    }
    @Override
    public String toString() {
        return id + " " + title + " " + completed;
    }
}​
```

