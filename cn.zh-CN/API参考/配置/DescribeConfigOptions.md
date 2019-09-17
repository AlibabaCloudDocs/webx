# DescribeConfigOptions {#doc_api_WebPlus_DescribeConfigOptions .reference}

调用DescribeConfigOptions查询配置选项信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeConfigOptions&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/config/configOption HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|否|ws-6c937c98a9c0296d0c48\*\*\*\*\*|环境ID

 |
|ProfileName|String|否|StandAlone|初始化配置类型，可选以下值：

 -   `HighAvailability`：高可用，该配置会将实例数设置为2，同时启用公网SLB
-   `StandAlone`：低成本，该配置会将实例数设置为1

 |
|StackId|String|否|we-5d3eaaea2977ca5251e\*\*\*\*\*|技术栈类型

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|EB4D295F-18CE-413D-85BE-EFCB508\*\*\*\*\*|请求ID

 |
|StackConfigOption| | |技术栈配置信息

 |
|ConfigOptions| | |配置选项列表

 |
|ChangeSeverity|String|NoInterruption|变更重要性

 |
|DefaultValue|String|“”|默认值

 |
|EditorType|String|\{"component":"Editor","props":\{\}\}|编辑类型

 |
|HiddenOption|Boolean|false|是否是隐藏选项

 |
|MaxLength|Integer|1024|最大长度

 |
|MaxValue|Long|-1|最大值

 |
|MinLength|Integer|0|最小长度

 |
|MinValue|Long|-1|最小值

 |
|OptionDescription|String|Web+ uses this command to launch an application|选项描述信息

 |
|OptionLabel|String|Start Command|可选项标签

 |
|OptionName|String|start|可选项名称

 |
|PathName|String|application.commands|路径名称

 |
|ReadonlyOption|Boolean|false|是否为只读选项

 |
|RegexDesc|String|“”|正则匹配描述

 |
|RegexPattern|String|“”|正则匹配模式

 |
|ValueOptions|String|“”|值类型的选项

 |
|ValueType|String|String|值类型

 |
|StackId|String|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈类型

 |
|StackName|String|Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903|技术栈名称

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/config/configOption?EnvId=we-5d3eaaea2977ca5251e*****&ProfileName=StandAlone&StackId=ws-6c937c98a9c0296d0c48*****&<公共请求头>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeConfigOptionsResponse>
    <Message>success</Message>
    <RequestId>EB4D295F-18CE-413D-85BE-EFCB508*****</RequestId>
    <StackConfigOption>
        <StackId>ws-6c937c98a9c0296d0c48*****</StackId>
        <ConfigOptions>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.commands</PathName>
                <OptionName>start</OptionName>
                <OptionLabel>Start Command</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ uses this command to launch an application</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.commands</PathName>
                <OptionName>stop</OptionName>
                <OptionLabel>Stop Command</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ uses this command to stop the application</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>JSON</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"KVListEditor","props":{}}</EditorType>
                <DefaultValue>[]</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.environmentVariables</PathName>
                <OptionName>value</OptionName>
                <OptionLabel>Environmental Variables</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16384</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The environment variable used to launch the app.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>http</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.healthCheck</PathName>
                <OptionName>type</OptionName>
                <OptionLabel>Health Check Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value": "http", "label": "HTTP"},{"value": "tcp", "label": "TCP"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The type of protocol used by the health check, currently supporting TCP and HTTP, Web+ will periodically send health check requests to the application's service port to determine if the application is healthy.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>/</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.healthCheck</PathName>
                <OptionName>path</OptionName>
                <OptionLabel>Health Check URL</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>256</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will request this URL and judge whether the application is healthy according to the response code. If a non-20x/30x response code is received or the response times out, it is determined that the single health check failed.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>3</DefaultValue>
                <MaxValue>30</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.healthCheck</PathName>
                <OptionName>retryCount</OptionName>
                <OptionLabel>Health Check Retry Count</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>If the health check retry exceeds this number, it is determined that the health check failed.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>3</DefaultValue>
                <MaxValue>60</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.healthCheck</PathName>
                <OptionName>intervalSeconds</OptionName>
                <OptionLabel>Health Check Interval (Seconds)</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>When an inspection fails, the interval to the next health check is long.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>3</DefaultValue>
                <MaxValue>60</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.healthCheck</PathName>
                <OptionName>timeoutSeconds</OptionName>
                <OptionLabel>Health Check Timeout (Seconds)</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The timeout period for a single health check.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"TextArea","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.jvmOpts</PathName>
                <OptionName>value</OptionName>
                <OptionLabel>JVM Options</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16384</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Set the Java virtual machine parameters used to launch the application.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1024</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>8080</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.option</PathName>
                <OptionName>port</OptionName>
                <OptionLabel>Server Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>This port will be used as the HTTP service port after the application is launched, and ports from 1024 to 65535 can be used.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>0</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>180</DefaultValue>
                <MaxValue>180</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.option</PathName>
                <OptionName>maxStartDuration</OptionName>
                <OptionLabel>Application Max Start Duration (Seconds)</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>If the health check status is still incorrect during this time after the application is started, the application is considered to have failed to start.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern>^[A-Za-z0-9_\-.]{1,64}$</RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.package</PathName>
                <OptionName>label</OptionName>
                <OptionLabel>Package Label</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will use this version of the deployment package to deploy ECS instances.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.package</PathName>
                <OptionName>storageKey</OptionName>
                <OptionLabel>Package File Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>256</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will deploy this file to the ECS instance.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.package</PathName>
                <OptionName>url</OptionName>
                <OptionLabel>Package URL</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Configure the URL of package.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"FileUploader","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.tomcatServerXml</PathName>
                <OptionName>serverConfig</OptionName>
                <OptionLabel>Tomcat Configuration File</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>256</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Use this file to replace Tomcat's server.xml configuration</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>hooks</PathName>
                <OptionName>prestart</OptionName>
                <OptionLabel>PreStart</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will call this command before the app starts</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>hooks</PathName>
                <OptionName>poststart</OptionName>
                <OptionLabel>PostStart</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will call this command after the app launches</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>hooks</PathName>
                <OptionName>prestop</OptionName>
                <OptionLabel>PreStop</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will call this command before the application stops</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>hooks</PathName>
                <OptionName>poststop</OptionName>
                <OptionLabel>PostStop</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will call this command after the app has stopped</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Editor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>hooks</PathName>
                <OptionName>postinit</OptionName>
                <OptionLabel>Postinit</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Web+ will call this command when the application is initialized</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>platform</PathName>
                <OptionName>stackName</OptionName>
                <OptionLabel>Software Stack</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Contains the operating system, development language, container type, etc.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>aliyunlinux</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>platform</PathName>
                <OptionName>os</OptionName>
                <OptionLabel>Operating System</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Operating system used</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>2.1903</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>platform</PathName>
                <OptionName>osVersion</OptionName>
                <OptionLabel>Operating System Version</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Operating system version used</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>tomcat 8 openjdk 8</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>platform</PathName>
                <OptionName>buildpack</OptionName>
                <OptionLabel>Buildpack</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Software development language and runtime container</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>Tomcat</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>platform</PathName>
                <OptionName>category</OptionName>
                <OptionLabel>Platform Category</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>JAVA, Tomcat, PHP, Go, etc.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>nginx</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>proxy</PathName>
                <OptionName>type</OptionName>
                <OptionLabel>Reverse Proxy Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>[{"value": "nginx", "label": "Nginx (1.14.2)"},{"value": "apache", "label": "Apache HTTP Server (2.4.6)"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The reverse proxy type used. After the reverse proxy starts, it will listen to the instance's port 80. Make sure that the port is not occupied by other programs. The reverse proxy will forward the received HTTP request to the application's service port.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>2.4.6</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>proxy.apache</PathName>
                <OptionName>version</OptionName>
                <OptionLabel>Apache HTTP Server Version</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value": "2.4.6", "label": "2.4.6"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Apache HTTP Server version used</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>1.14.2</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>proxy.nginx</PathName>
                <OptionName>version</OptionName>
                <OptionLabel>Nginx Version</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value": "1.14.2", "label": "1.14.2"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Nginx version used</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>List</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"InstanceTypeSelector","props":{"mode":"multiple"}}</EditorType>
                <DefaultValue>["ecs.t5-lc1m1.small","ecs.xn4.small","ecs.n1.tiny","ecs.g5.large"]</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>instanceType</OptionName>
                <OptionLabel>Instance Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>10</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The instance specification used by the deployment environment, Web+ will create an ECS instance using the selected specifications. Multiple specifications can be selected. When the selected specifications are insufficient, Web+ will attempt to create in the order selected, up to 10 instance specifications. An ECS instance created by Web+, using the//help.aliyun.com/knowledge_detail/40653.html"&gt;Pay As You Go&gt;</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>wp-autoscaled</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>instanceName</OptionName>
                <OptionLabel>Instance Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>128</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>1</MinLength>
                <OptionDescription>Instance name used</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>0</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>1</DefaultValue>
                <MaxValue>100</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>instanceNum</OptionName>
                <OptionLabel>Instance Number</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The number of instances used, Web+ will expand or shrink the deployment environment based on this number.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>List</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"SecurityGroupSelector","props":{"mode":"multiple"}}</EditorType>
                <DefaultValue>[]</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>securityGroupIds</OptionName>
                <OptionLabel>Security Groups</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>5</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The security group used by the instance can select up to 5 security groups.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>AliyunECSInstanceForWebPlusRole</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>ramRoleName</OptionName>
                <OptionLabel>ECS RAM Role Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>RAM role name used by ECS instances created by Web+</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"KeyPairSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>keyPairName</OptionName>
                <OptionLabel>Key Pair Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Key pair, used for SSH login, please refer to           <a href="//help.aliyun.com/document_detail/51793.html" target="_blank">Using SSH key pair</a>        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>release</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>scalingPolicy</OptionName>
                <OptionLabel>Scaling Policy</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value":"recycle","label":"{{webx.configvalue.resources-ecs-autoScaling.scalingPolicy.recycle.msg}}"},{"value":"release","label":"{{webx.configvalue.resources-ecs-autoScaling.scalingPolicy.recycle.msg}}"}]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Recycling mode when the ECS instance is shrunk, optional release mode or shutdown recovery mode.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>userData</OptionName>
                <OptionLabel>User Data</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16384</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Configure ECS user data, refer to           <a href="//help.aliyun.com/video_detail/54745.html" targe="_blank"> ECS User Data Practices</a>.        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"DataDiskEditor","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>dataDiskInfo</OptionName>
                <OptionLabel>Data Disk Infomation</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Configure information about the data disk.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>40</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>100</DefaultValue>
                <MaxValue>500</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>systemDiskSize</OptionName>
                <OptionLabel>System Disk Size</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>System disk size (GB)</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>cloud_efficiency</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>systemDiskCategory</OptionName>
                <OptionLabel>System Disk Category</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["cloud","cloud_efficiency","cloud_ssd","ephemeral_ssd"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>1</MinLength>
                <OptionDescription>The disk type of the system disk, optional: cloud, cloud_efficiency, cloud_ssd, ephemeral_ssd.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>BALANCE</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>multiAzPolicy</OptionName>
                <OptionLabel>Multiple Zones Policy</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["PRIORITY","COST_OPTIMIZED","BALANCE"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>1</MinLength>
                <OptionDescription>Multi-AZ scaling group used by Web+ ECS instance expansion and contraction strategy, optional priority policy or balancing policy.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>true</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>enableInternet</OptionName>
                <OptionLabel>Enable Public IP</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Whether the public network IP address is enabled. If enabled, the ECS instance in the deployment environment can be accessed from the public network. Pay attention to the security configuration. The public network service provided by the ECS instance may incur charges. Please refer to           <a href="// Help.aliyun.com/document_detail/25411.html" target="_blank">public network bandwidth billing</a>.        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>PayByTraffic</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>internetChargeType</OptionName>
                <OptionLabel>Internet Charge Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["PayByBandwidth","PayByTraffic"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>1</MinLength>
                <OptionDescription>The network charge type can be selected to be charged by flow rate or by bandwidth.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>100</DefaultValue>
                <MaxValue>200</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>internetMaxBandwidthIn</OptionName>
                <OptionLabel>Max Bandwidth Inbound</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The maximum bandwidth of the public network is in Mbps (Mega bit per second), and the value ranges from 1 to 200.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>0</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>50</DefaultValue>
                <MaxValue>100</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>internetMaxBandwidthOut</OptionName>
                <OptionLabel>Max Bandwidth Outbound</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The maximum bandwidth of the public network, in Mbps (Mega bit per second), the value range is 0-100.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>true</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>ioOptimized</OptionName>
                <OptionLabel>IO Optimized</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Whether to create I/O optimization instances.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>false</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.ecs.autoScaling</PathName>
                <OptionName>passwordInherit</OptionName>
                <OptionLabel>Password Inherit</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Whether to use the password of the mirror preset. When using this parameter, the password used by the mirror must be preset.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>JSON</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"VpcOptionSelector","props":{}}</EditorType>
                <DefaultValue>{"vpcId":"","vSwitches":[]}</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.network</PathName>
                <OptionName>vpcOption</OptionName>
                <OptionLabel>Network Options</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>For VPCs and switches used in the deployment environment, if multiple switches are selected, Web+ will distribute the ECS instances equally across the selected switches. New VPCs and switches can be created in the //vpc.console.aliyun.com" target="_blank"&gt;VPC console</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>false</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>enable</OptionName>
                <OptionLabel>Enable</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The Aliyun Relational Database Service is a stable, resilient, scalable online database service that supports MySQL, SQL Server, PostgreSQL, PPAS, and MariaDB TX engines. It also provides a complete solution for disaster tolerance, backup, recovery, monitoring, migration, and more. For more information, please refer to          <a target="_blank" href="//help.aliyun.com/knowledge_detail/26092.html">What is Cloud Database RDS</a>        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>false</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>imported</OptionName>
                <OptionLabel>Use existed instance</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Please import an existing RDS instance. Under this scenario, you need to ensure that the corresponding database, account and password exist on the instance. And Web+ will send the provided connection information to the application.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>rdsId</OptionName>
                <OptionLabel>Database Instance</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Please select the database instance you want to import</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSZoneSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>zoneId</OptionName>
                <OptionLabel>Zone</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Please select the available zone where the RDS instance is located</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>JSON</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSVSwitchSelector","props":{}}</EditorType>
                <DefaultValue>[]</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>vSwitches</OptionName>
                <OptionLabel>Zone and VSwitch</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Please select the zone and switch where the RDS instance is located (the star-marked switch is the default switch for the current environment)</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSEngineSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>engine</OptionName>
                <OptionLabel>Database Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>RDS supports database types such as MySQL, PostgreSQL, SQL Server, MariaDB TX, and PPAS (Postgre Plus Advanced Server, highly compatible Oracle Database).</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSEngineVersionSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>engineVersion</OptionName>
                <OptionLabel>Database version</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Choose the right database engine version for your business needs</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSStorageTypeSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>storageType</OptionName>
                <OptionLabel>Storage Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>to meet the needs of different scenarios, cloud database RDS offers three types of data storage: local_ssd , cloud_ssd, and cloud_essd. It is recommended to use the local SSD disk to store data on the local SSD disk, which can reduce I/O latency. Detail can be referenced here           <a target="_blank" href="//help.aliyun.com/knowledge_detail/69795.html">Storage type</a>。        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>5</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSStorageSizeSelector","props":{}}</EditorType>
                <DefaultValue>100</DefaultValue>
                <MaxValue>10000</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>storageSize</OptionName>
                <OptionLabel>Storage size</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Choose the right storage size for your business needs (in GB)</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSInstanceClassSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>dbInstanceClass</OptionName>
                <OptionLabel>Instance Class</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Cloud database RDS offers two instance size families, both generic and exclusive. Generic instance has universal exclusive allocated memory and I/O resources but share CPU and storage resources with other generic instances on the same physical machine. Exclusive instance has exclusive cpu, memory, storage, and I/O resources and  performance that is not affected by the behavior of other instances on the physical machine.See in detail          <a target="_blank" href="//help.aliyun.com/knowledge_detail/57184.html">Instance Specification Family</a>。        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>webplus</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>databaseName</OptionName>
                <OptionLabel>Database Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The name of the database. Under purchasing scenario, Web+ will help you create the database (except PostgreSQL, PPAS, and SQL Server 2017 Cluster Edition, which you can do with CREATE DATABASE in SQL), and under the import scenario you need to ensure that the database already exists.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSCharacterSetSelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>characterSetName</OptionName>
                <OptionLabel>Character Set</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>64</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The character set of the database, MySQL and MariaDB by default takes utf8mb4, SQL Server by default takes Chinese-PRC-CI-AS</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>webplus</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>accountName</OptionName>
                <OptionLabel>Account Name</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The database account. Under the purchasing scenario, Web+ will help you create and maintain this account on the instance, and under the import scenario you need to ensure that the account is correct.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSAccountPassword","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>accountPassword</OptionName>
                <OptionLabel>Password</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The password of the database account. Under the purchasing scenario, Web+ will ensure that the account is consistent with the password, and under the import scene you need to ensure that the password is correct.(Password rule is: uppercase, lowercase, number, special characters accounted for three, length 8-32 bits, special characters for </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"RDSCategorySelector","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.rds</PathName>
                <OptionName>category</OptionName>
                <OptionLabel>Category</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>1024</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Cloud database RDS include four series: Basic, High Available, Cluster, and Financial. Details can be found here          <a target="_blank" href="//help.aliyun.com/document_detail/55665.html">Overview of the product line</a>。        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{"enableLabel":"When this option is enabled, the application will be accessible from the public network. Please pay attention to your security configuration."}}</EditorType>
                <DefaultValue>false</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>enable</OptionName>
                <OptionLabel>Enable Internet SLB</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Whether to enable the public network SLB, if there are multiple instances of the deployment environment, you can use SLB for load balancing, which can be controlled in           <a href="//slb.console.aliyun.com" target="_blank">SLB Desk</a> creates or configures an SLB.        </OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"SLBSelector","props":{"AddressType":"internet"}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>slbId</OptionName>
                <OptionLabel>Internet SLB</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Use an existing SLB instance or automatically purchase an SLB instance from Web+.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>80</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>listenerPort</OptionName>
                <OptionLabel>Internet SLB Listener Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The listening port of the public network SLB can use this port to access applications from the public network.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>http</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>protocol</OptionName>
                <OptionLabel>Internet SLB Protocol</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value":"tcp","label":"TCP"},{"value":"http","label":"HTTP"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Protocol used by the internet SLB</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>forwardingRule</OptionName>
                <OptionLabel>Internet SLB Forwarding Rule</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>128</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Forwarding rules used by the internet SLB. The forwarding rule is in the format of Host / Path, and Host or Path needs to configure at least one item, such as www.taobao.com/test, www.taobao.com, /test are all correct forwarding rules.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>80</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>backendPort</OptionName>
                <OptionLabel>Internet SLB Backend Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The internet SLB forwards the request to the port of the instance, which is generally the application reverse proxy port</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>-1</DefaultValue>
                <MaxValue>5120</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>bandwidth</OptionName>
                <OptionLabel>Max Bandwidth</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The peak bandwidth of the load balancer.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>slb.s1.small</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>loadBalancerSpec</OptionName>
                <OptionLabel>Load Balancer Spec</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["slb.s1.small","slb.s2.small","slb.s2.medium","slb.s3.small","slb.s3.medium","slb.s3.large"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The specifications of the load balancing instance.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>/</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>healthCheckUrl</OptionName>
                <OptionLabel>Health Check URL</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>256</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>URL path for health checks.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>paybytraffic</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.internet</PathName>
                <OptionName>internetChargeType</OptionName>
                <OptionLabel>Internet Charge Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["paybybandwidth","paybytraffic"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The payment method of the public network type instance can be charged by bandwidth or by flow meter.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Boolean</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Switch","props":{}}</EditorType>
                <DefaultValue>false</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>enable</OptionName>
                <OptionLabel>Enable Intranet SLB</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Whether to enable intranet SLB, if there are multiple instances in the deployment environment, you can use SLB for load balancing, which can be used in //slb.console.aliyun.com SLB console Create or configure SLB.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"SLBSelector","props":{"AddressType":"intranet"}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>slbId</OptionName>
                <OptionLabel>Intranet SLB</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Use an existing SLB instance or automatically purchase an SLB instance from Web+.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>80</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>listenerPort</OptionName>
                <OptionLabel>Intranet SLB Listener Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Intranet SLB listening port, use this port to access applications from the intranet.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>http</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>protocol</OptionName>
                <OptionLabel>Intranet SLB Protocol</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>16</MaxLength>
                <ValueOptions>[{"value":"tcp","label":"TCP"},{"value":"http","label":"HTTP"}]</ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Protocol used by the intranet SLB</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue></DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>forwardingRule</OptionName>
                <OptionLabel>Intranet SLB Forwarding Rule</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>128</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>Forwarding rules used by the intranet SLB. The forwarding rule is in the format of Host / Path, and Host or Path needs to configure at least one item, such as www.taobao.com/test, www.taobao.com, /test are all correct forwarding rules.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>80</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>backendPort</OptionName>
                <OptionLabel>Intranet SLB Backend Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>true</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The intranet SLB forwards the request to the port of the instance, which is generally the application reverse proxy port</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>-1</DefaultValue>
                <MaxValue>5120</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>bandwidth</OptionName>
                <OptionLabel>Max Bandwidth</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The peak bandwidth of the load balancer.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>slb.s1.small</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>loadBalancerSpec</OptionName>
                <OptionLabel>Load Balancer Spec</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["slb.s1.small","slb.s2.small","slb.s2.medium","slb.s3.small","slb.s3.medium","slb.s3.large"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The specifications of the load balancing instance.</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Input","props":{}}</EditorType>
                <DefaultValue>/</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>healthCheckUrl</OptionName>
                <OptionLabel>健康检查URL</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>256</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>用于健康检查的URL路径。</OptionDescription>
            </ConfigOption>
            <ConfigOption>
                <MinValue>-1</MinValue>
                <ValueType>String</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"Select","props":{}}</EditorType>
                <DefaultValue>paybytraffic</DefaultValue>
                <MaxValue>-1</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>resources.slb.intranet</PathName>
                <OptionName>internetChargeType</OptionName>
                <OptionLabel>Charge Type</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>32</MaxLength>
                <ValueOptions>["paybybandwidth","paybytraffic"]</ValueOptions>
                <HiddenOption>true</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>The payment method of the SLB instance can be charged by bandwidth or by flow meter.</OptionDescription>
            </ConfigOption>
        </ConfigOptions>
        <StackName>Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903</StackName>
    </StackConfigOption>
    <Code>OK</Code>
</DescribeConfigOptionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"B645371A-29E9-4124-949E-38E42F5*****",
	"StackConfigOption":{
		"StackId":"ws-6c937c98a9c0296d0c48*****",
		"ConfigOptions":{
			"ConfigOption":[
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.commands",
					"OptionName":"start",
					"OptionLabel":"Start Command",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ uses this command to launch an application"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.commands",
					"OptionName":"stop",
					"OptionLabel":"Stop Command",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ uses this command to stop the application"
				},
				{
					"MinValue":-1,
					"ValueType":"JSON",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"KVListEditor\",\"props\":{}}",
					"DefaultValue":"[]",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.environmentVariables",
					"OptionName":"value",
					"OptionLabel":"Environmental Variables",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16384,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The environment variable used to launch the app."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"http",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.healthCheck",
					"OptionName":"type",
					"OptionLabel":"Health Check Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\": \"http\", \"label\": \"HTTP\"},{\"value\": \"tcp\", \"label\": \"TCP\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The type of protocol used by the health check, currently supporting TCP and HTTP, Web+ will periodically send health check requests to the application's service port to determine if the application is healthy."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"/",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.healthCheck",
					"OptionName":"path",
					"OptionLabel":"Health Check URL",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":256,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will request this URL and judge whether the application is healthy according to the response code. If a non-20x/30x response code is received or the response times out, it is determined that the single health check failed."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"3",
					"RegexDesc":"",
					"MaxValue":30,
					"PathName":"application.healthCheck",
					"OptionName":"retryCount",
					"OptionLabel":"Health Check Retry Count",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"If the health check retry exceeds this number, it is determined that the health check failed."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"3",
					"RegexDesc":"",
					"MaxValue":60,
					"PathName":"application.healthCheck",
					"OptionName":"intervalSeconds",
					"OptionLabel":"Health Check Interval (Seconds)",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"When an inspection fails, the interval to the next health check is long."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"3",
					"RegexDesc":"",
					"MaxValue":60,
					"PathName":"application.healthCheck",
					"OptionName":"timeoutSeconds",
					"OptionLabel":"Health Check Timeout (Seconds)",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The timeout period for a single health check."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"TextArea\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.jvmOpts",
					"OptionName":"value",
					"OptionLabel":"JVM Options",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16384,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Set the Java virtual machine parameters used to launch the application."
				},
				{
					"MinValue":1024,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"8080",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"application.option",
					"OptionName":"port",
					"OptionLabel":"Server Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"This port will be used as the HTTP service port after the application is launched, and ports from 1024 to 65535 can be used."
				},
				{
					"MinValue":0,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"180",
					"RegexDesc":"",
					"MaxValue":180,
					"PathName":"application.option",
					"OptionName":"maxStartDuration",
					"OptionLabel":"Application Max Start Duration (Seconds)",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"If the health check status is still incorrect during this time after the application is started, the application is considered to have failed to start."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"^[A-Za-z0-9_\\-.]{1,64}$",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.package",
					"OptionName":"label",
					"OptionLabel":"Package Label",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Web+ will use this version of the deployment package to deploy ECS instances."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.package",
					"OptionName":"storageKey",
					"OptionLabel":"Package File Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":256,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Web+ will deploy this file to the ECS instance."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.package",
					"OptionName":"url",
					"OptionLabel":"Package URL",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Configure the URL of package."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"FileUploader\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"application.tomcatServerXml",
					"OptionName":"serverConfig",
					"OptionLabel":"Tomcat Configuration File",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":256,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Use this file to replace Tomcat's server.xml configuration"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"hooks",
					"OptionName":"prestart",
					"OptionLabel":"PreStart",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will call this command before the app starts"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"hooks",
					"OptionName":"poststart",
					"OptionLabel":"PostStart",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will call this command after the app launches"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"hooks",
					"OptionName":"prestop",
					"OptionLabel":"PreStop",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will call this command before the application stops"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"hooks",
					"OptionName":"poststop",
					"OptionLabel":"PostStop",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will call this command after the app has stopped"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Editor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"hooks",
					"OptionName":"postinit",
					"OptionLabel":"Postinit",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Web+ will call this command when the application is initialized"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"platform",
					"OptionName":"stackName",
					"OptionLabel":"Software Stack",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Contains the operating system, development language, container type, etc."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"aliyunlinux",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"platform",
					"OptionName":"os",
					"OptionLabel":"Operating System",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Operating system used"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"2.1903",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"platform",
					"OptionName":"osVersion",
					"OptionLabel":"Operating System Version",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":16,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Operating system version used"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"tomcat 8 openjdk 8",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"platform",
					"OptionName":"buildpack",
					"OptionLabel":"Buildpack",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Software development language and runtime container"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"Tomcat",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"platform",
					"OptionName":"category",
					"OptionLabel":"Platform Category",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"JAVA, Tomcat, PHP, Go, etc."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"nginx",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"proxy",
					"OptionName":"type",
					"OptionLabel":"Reverse Proxy Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[{\"value\": \"nginx\", \"label\": \"Nginx (1.14.2)\"},{\"value\": \"apache\", \"label\": \"Apache HTTP Server (2.4.6)\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The reverse proxy type used. After the reverse proxy starts, it will listen to the instance's port 80. Make sure that the port is not occupied by other programs. The reverse proxy will forward the received HTTP request to the application's service port."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"2.4.6",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"proxy.apache",
					"OptionName":"version",
					"OptionLabel":"Apache HTTP Server Version",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\": \"2.4.6\", \"label\": \"2.4.6\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Apache HTTP Server version used"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"1.14.2",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"proxy.nginx",
					"OptionName":"version",
					"OptionLabel":"Nginx Version",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\": \"1.14.2\", \"label\": \"1.14.2\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Nginx version used"
				},
				{
					"MinValue":-1,
					"ValueType":"List",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"InstanceTypeSelector\",\"props\":{\"mode\":\"multiple\"}}",
					"DefaultValue":"[\"ecs.t5-lc1m1.small\",\"ecs.xn4.small\",\"ecs.n1.tiny\",\"ecs.g5.large\"]",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"instanceType",
					"OptionLabel":"Instance Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":10,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The instance specification used by the deployment environment, Web+ will create an ECS instance using the selected specifications. Multiple specifications can be selected. When the selected specifications are insufficient, Web+ will attempt to create in the order selected, up to 10 instance specifications. An ECS instance created by Web+, using the <a target=\"_blank\" href=\"//help.aliyun.com/knowledge_detail/40653.html\">Pay As You Go</a>."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"wp-autoscaled",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"instanceName",
					"OptionLabel":"Instance Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":128,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":1,
					"OptionDescription":"Instance name used"
				},
				{
					"MinValue":0,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"1",
					"RegexDesc":"",
					"MaxValue":100,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"instanceNum",
					"OptionLabel":"Instance Number",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The number of instances used, Web+ will expand or shrink the deployment environment based on this number."
				},
				{
					"MinValue":-1,
					"ValueType":"List",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"SecurityGroupSelector\",\"props\":{\"mode\":\"multiple\"}}",
					"DefaultValue":"[]",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"securityGroupIds",
					"OptionLabel":"Security Groups",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":5,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The security group used by the instance can select up to 5 security groups."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"AliyunECSInstanceForWebPlusRole",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"ramRoleName",
					"OptionLabel":"ECS RAM Role Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"RAM role name used by ECS instances created by Web+"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"KeyPairSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"keyPairName",
					"OptionLabel":"Key Pair Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Key pair, used for SSH login, please refer to <a href=\"//help.aliyun.com/document_detail/51793.html\" target=\"_blank\">Using SSH key pair</a>."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"release",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"scalingPolicy",
					"OptionLabel":"Scaling Policy",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\":\"recycle\",\"label\":\"{{webx.configvalue.resources-ecs-autoScaling.scalingPolicy.recycle.msg}}\"},{\"value\":\"release\",\"label\":\"{{webx.configvalue.resources-ecs-autoScaling.scalingPolicy.recycle.msg}}\"}]",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Recycling mode when the ECS instance is shrunk, optional release mode or shutdown recovery mode."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"userData",
					"OptionLabel":"User Data",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16384,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Configure ECS user data, refer to <a href=\"//help.aliyun.com/video_detail/54745.html\" targe=\"_blank\"> ECS User Data Practices</a>."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"DataDiskEditor\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"dataDiskInfo",
					"OptionLabel":"Data Disk Infomation",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Configure information about the data disk."
				},
				{
					"MinValue":40,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"100",
					"RegexDesc":"",
					"MaxValue":500,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"systemDiskSize",
					"OptionLabel":"System Disk Size",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"System disk size (GB)"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"cloud_efficiency",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"systemDiskCategory",
					"OptionLabel":"System Disk Category",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"cloud\",\"cloud_efficiency\",\"cloud_ssd\",\"ephemeral_ssd\"]",
					"HiddenOption":true,
					"MinLength":1,
					"OptionDescription":"The disk type of the system disk, optional: cloud, cloud_efficiency, cloud_ssd, ephemeral_ssd."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"BALANCE",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"multiAzPolicy",
					"OptionLabel":"Multiple Zones Policy",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"PRIORITY\",\"COST_OPTIMIZED\",\"BALANCE\"]",
					"HiddenOption":true,
					"MinLength":1,
					"OptionDescription":"Multi-AZ scaling group used by Web+ ECS instance expansion and contraction strategy, optional priority policy or balancing policy."
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"true",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"enableInternet",
					"OptionLabel":"Enable Public IP",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Whether the public network IP address is enabled. If enabled, the ECS instance in the deployment environment can be accessed from the public network. Pay attention to the security configuration. The public network service provided by the ECS instance may incur charges. Please refer to <a href=\"// Help.aliyun.com/document_detail/25411.html\" target=\"_blank\">public network bandwidth billing</a>."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"PayByTraffic",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"internetChargeType",
					"OptionLabel":"Internet Charge Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"PayByBandwidth\",\"PayByTraffic\"]",
					"HiddenOption":true,
					"MinLength":1,
					"OptionDescription":"The network charge type can be selected to be charged by flow rate or by bandwidth."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"100",
					"RegexDesc":"",
					"MaxValue":200,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"internetMaxBandwidthIn",
					"OptionLabel":"Max Bandwidth Inbound",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The maximum bandwidth of the public network is in Mbps (Mega bit per second), and the value ranges from 1 to 200."
				},
				{
					"MinValue":0,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"50",
					"RegexDesc":"",
					"MaxValue":100,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"internetMaxBandwidthOut",
					"OptionLabel":"Max Bandwidth Outbound",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The maximum bandwidth of the public network, in Mbps (Mega bit per second), the value range is 0-100."
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"true",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"ioOptimized",
					"OptionLabel":"IO Optimized",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Whether to create I/O optimization instances."
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"false",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.ecs.autoScaling",
					"OptionName":"passwordInherit",
					"OptionLabel":"Password Inherit",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"Whether to use the password of the mirror preset. When using this parameter, the password used by the mirror must be preset."
				},
				{
					"MinValue":-1,
					"ValueType":"JSON",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"VpcOptionSelector\",\"props\":{}}",
					"DefaultValue":"{\"vpcId\":\"\",\"vSwitches\":[]}",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.network",
					"OptionName":"vpcOption",
					"OptionLabel":"Network Options",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"For VPCs and switches used in the deployment environment, if multiple switches are selected, Web+ will distribute the ECS instances equally across the selected switches. New VPCs and switches can be created in the <a href=\"//vpc.console.aliyun.com\" target=\"_blank\">VPC console</a>."
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"false",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"enable",
					"OptionLabel":"Enable",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The Aliyun Relational Database Service is a stable, resilient, scalable online database service that supports MySQL, SQL Server, PostgreSQL, PPAS, and MariaDB TX engines. It also provides a complete solution for disaster tolerance, backup, recovery, monitoring, migration, and more. For more information, please refer to<a target=\"_blank\" href=\"//help.aliyun.com/knowledge_detail/26092.html\">What is Cloud Database RDS</a>。"
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"false",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"imported",
					"OptionLabel":"Use existed instance",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Please import an existing RDS instance. Under this scenario, you need to ensure that the corresponding database, account and password exist on the instance. And Web+ will send the provided connection information to the application."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"rdsId",
					"OptionLabel":"Database Instance",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Please select the database instance you want to import"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSZoneSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"zoneId",
					"OptionLabel":"Zone",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Please select the available zone where the RDS instance is located"
				},
				{
					"MinValue":-1,
					"ValueType":"JSON",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSVSwitchSelector\",\"props\":{}}",
					"DefaultValue":"[]",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"vSwitches",
					"OptionLabel":"Zone and VSwitch",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Please select the zone and switch where the RDS instance is located (the star-marked switch is the default switch for the current environment)"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSEngineSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"engine",
					"OptionLabel":"Database Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"RDS supports database types such as MySQL, PostgreSQL, SQL Server, MariaDB TX, and PPAS (Postgre Plus Advanced Server, highly compatible Oracle Database)."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSEngineVersionSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"engineVersion",
					"OptionLabel":"Database version",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Choose the right database engine version for your business needs"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSStorageTypeSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"storageType",
					"OptionLabel":"Storage Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"To meet the needs of different scenarios, cloud database RDS offers three types of data storage: local_ssd , cloud_ssd, and cloud_essd. It is recommended to use the local SSD disk to store data on the local SSD disk, which can reduce I/O latency. Detail can be referenced here <a target=\"_blank\" href=\"//help.aliyun.com/knowledge_detail/69795.html\">Storage type</a>。"
				},
				{
					"MinValue":5,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSStorageSizeSelector\",\"props\":{}}",
					"DefaultValue":"100",
					"RegexDesc":"",
					"MaxValue":10000,
					"PathName":"resources.rds",
					"OptionName":"storageSize",
					"OptionLabel":"Storage size",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Choose the right storage size for your business needs (in GB)"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSInstanceClassSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"dbInstanceClass",
					"OptionLabel":"Instance Class",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Cloud database RDS offers two instance size families, both generic and exclusive. Generic instance has universal exclusive allocated memory and I/O resources but share CPU and storage resources with other generic instances on the same physical machine. Exclusive instance has exclusive cpu, memory, storage, and I/O resources and  performance that is not affected by the behavior of other instances on the physical machine.See in detail<a target=\"_blank\" href=\"//help.aliyun.com/knowledge_detail/57184.html\">Instance Specification Family</a>。"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"webplus",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"databaseName",
					"OptionLabel":"Database Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The name of the database. Under purchasing scenario, Web+ will help you create the database (except PostgreSQL, PPAS, and SQL Server 2017 Cluster Edition, which you can do with CREATE DATABASE in SQL), and under the import scenario you need to ensure that the database already exists."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSCharacterSetSelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"characterSetName",
					"OptionLabel":"Character Set",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":64,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The character set of the database, MySQL and MariaDB by default takes utf8mb4, SQL Server by default takes Chinese-PRC-CI-AS"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"webplus",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"accountName",
					"OptionLabel":"Account Name",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The database account. Under the purchasing scenario, Web+ will help you create and maintain this account on the instance, and under the import scenario you need to ensure that the account is correct."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSAccountPassword\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"accountPassword",
					"OptionLabel":"Password",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The password of the database account. Under the purchasing scenario, Web+ will ensure that the account is consistent with the password, and under the import scene you need to ensure that the password is correct.(Password rule is: uppercase, lowercase, number, special characters accounted for three, length 8-32 bits, special characters for !@#$%^&*()_+-= )"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"RDSCategorySelector\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.rds",
					"OptionName":"category",
					"OptionLabel":"Category",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":1024,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Cloud database RDS include four series: Basic, High Available, Cluster, and Financial. Details can be found here<a target=\"_blank\" href=\"//help.aliyun.com/document_detail/55665.html\">Overview of the product line</a>。"
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{\"enableLabel\":\"When this option is enabled, the application will be accessible from the public network. Please pay attention to your security configuration.\"}}",
					"DefaultValue":"false",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"enable",
					"OptionLabel":"Enable Internet SLB",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Whether to enable the public network SLB, if there are multiple instances of the deployment environment, you can use SLB for load balancing, which can be controlled in <a href=\"//slb.console.aliyun.com\" target=\"_blank\">SLB Desk</a> creates or configures an SLB."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"SLBSelector\",\"props\":{\"AddressType\":\"internet\"}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"slbId",
					"OptionLabel":"Internet SLB",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Use an existing SLB instance or automatically purchase an SLB instance from Web+."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"80",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"resources.slb.internet",
					"OptionName":"listenerPort",
					"OptionLabel":"Internet SLB Listener Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"The listening port of the public network SLB can use this port to access applications from the public network."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"http",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"protocol",
					"OptionLabel":"Internet SLB Protocol",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\":\"tcp\",\"label\":\"TCP\"},{\"value\":\"http\",\"label\":\"HTTP\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Protocol used by the internet SLB"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"forwardingRule",
					"OptionLabel":"Internet SLB Forwarding Rule",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":128,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Forwarding rules used by the internet SLB. The forwarding rule is in the format of Host / Path, and Host or Path needs to configure at least one item, such as www.taobao.com/test, www.taobao.com, /test are all correct forwarding rules."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"80",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"resources.slb.internet",
					"OptionName":"backendPort",
					"OptionLabel":"Internet SLB Backend Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The internet SLB forwards the request to the port of the instance, which is generally the application reverse proxy port"
				},
				{
					"MinValue":-1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"-1",
					"RegexDesc":"",
					"MaxValue":5120,
					"PathName":"resources.slb.internet",
					"OptionName":"bandwidth",
					"OptionLabel":"Max Bandwidth",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The peak bandwidth of the load balancer."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"slb.s1.small",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"loadBalancerSpec",
					"OptionLabel":"Load Balancer Spec",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"slb.s1.small\",\"slb.s2.small\",\"slb.s2.medium\",\"slb.s3.small\",\"slb.s3.medium\",\"slb.s3.large\"]",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The specifications of the load balancing instance."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"/",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"healthCheckUrl",
					"OptionLabel":"Health Check URL",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":256,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"URL path for health checks."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"paybytraffic",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.internet",
					"OptionName":"internetChargeType",
					"OptionLabel":"Internet Charge Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"paybybandwidth\",\"paybytraffic\"]",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The payment method of the public network type instance can be charged by bandwidth or by flow meter."
				},
				{
					"MinValue":-1,
					"ValueType":"Boolean",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Switch\",\"props\":{}}",
					"DefaultValue":"false",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"enable",
					"OptionLabel":"Enable Intranet SLB",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Whether to enable intranet SLB, if there are multiple instances in the deployment environment, you can use SLB for load balancing, which can be used in <a href=\"//slb.console.aliyun.com\" target=\"_blank\">SLB console</ a>Create or configure SLB."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"SLBSelector\",\"props\":{\"AddressType\":\"intranet\"}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"slbId",
					"OptionLabel":"Intranet SLB",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Use an existing SLB instance or automatically purchase an SLB instance from Web+."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"80",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"resources.slb.intranet",
					"OptionName":"listenerPort",
					"OptionLabel":"Intranet SLB Listener Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Intranet SLB listening port, use this port to access applications from the intranet."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"http",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"protocol",
					"OptionLabel":"Intranet SLB Protocol",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":16,
					"ValueOptions":"[{\"value\":\"tcp\",\"label\":\"TCP\"},{\"value\":\"http\",\"label\":\"HTTP\"}]",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Protocol used by the intranet SLB"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"forwardingRule",
					"OptionLabel":"Intranet SLB Forwarding Rule",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":128,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"Forwarding rules used by the intranet SLB. The forwarding rule is in the format of Host / Path, and Host or Path needs to configure at least one item, such as www.taobao.com/test, www.taobao.com, /test are all correct forwarding rules."
				},
				{
					"MinValue":1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"80",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"resources.slb.intranet",
					"OptionName":"backendPort",
					"OptionLabel":"Intranet SLB Backend Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":true,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The intranet SLB forwards the request to the port of the instance, which is generally the application reverse proxy port"
				},
				{
					"MinValue":-1,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"-1",
					"RegexDesc":"",
					"MaxValue":5120,
					"PathName":"resources.slb.intranet",
					"OptionName":"bandwidth",
					"OptionLabel":"Max Bandwidth",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The peak bandwidth of the load balancer."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"slb.s1.small",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"loadBalancerSpec",
					"OptionLabel":"Load Balancer Spec",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"slb.s1.small\",\"slb.s2.small\",\"slb.s2.medium\",\"slb.s3.small\",\"slb.s3.medium\",\"slb.s3.large\"]",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The specifications of the load balancing instance."
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Input\",\"props\":{}}",
					"DefaultValue":"/",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"healthCheckUrl",
					"OptionLabel":"健康检查URL",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":256,
					"ValueOptions":"",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"用于健康检查的URL路径。"
				},
				{
					"MinValue":-1,
					"ValueType":"String",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"Select\",\"props\":{}}",
					"DefaultValue":"paybytraffic",
					"RegexDesc":"",
					"MaxValue":-1,
					"PathName":"resources.slb.intranet",
					"OptionName":"internetChargeType",
					"OptionLabel":"Charge Type",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":32,
					"ValueOptions":"[\"paybybandwidth\",\"paybytraffic\"]",
					"HiddenOption":true,
					"MinLength":0,
					"OptionDescription":"The payment method of the SLB instance can be charged by bandwidth or by flow meter."
				}
			]
		},
		"StackName":"Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

