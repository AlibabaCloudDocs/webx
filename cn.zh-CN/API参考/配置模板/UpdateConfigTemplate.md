# UpdateConfigTemplate {#doc_api_WebPlus_UpdateConfigTemplate .reference}

调用UpdateConfigTemplate来更新配置模板。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=UpdateConfigTemplate&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
PUT /pop/v1/wam/configTemplate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|TemplateId|String|是|wct-5d1eca8dd56beb2b7\*\*\*\*\*|模板ID

 |
|OptionSettings|String|否|\[\{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"\}, \{"path":"application.option", "name":"port","value":"8081"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|TemplateDescription|String|否|This is a template|模板描述信息

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|ConfigTemplate| | |配置模板信息

 |
|AppId|String|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID，模板所在应用ID

 |
|AppName|String|app1|模板所在应用名称

 |
|CreateTime|Long|1562299021581|模板创建时间

 |
|StackId|String|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈ID

 |
|StackName|String|Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903|技术栈名称

 |
|TemplateId|String|wct-5d1eca8dd56beb722b7\*\*\*\*\*|模板ID

 |
|TemplateName|String|new-template-name|模板名称

 |
|UpdateTime|Long|1562587235328|上次更新时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|CE6E878B-DDB4-4563-9263-D75057C\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/configTemplate?ServiceCode=webx&<公共请求参数>
{
  "TemplateId":"wct-5d1eca8dd56beb2b7*****",
  "TemplateDescription":"This is a template",
  "OptionSettings":"[{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"},     {"path":"application.option", "name":"port","value":"8081"}]"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateConfigTemplateResponse>
    <ConfigTemplate>
        <TemplateName>new-template-name</TemplateName>
        <StackId>ws-6c937c98a9c0296d0c48*****</StackId>
        <CreateTime>1562299021581</CreateTime>
        <AppId>wa-5d1d9d8c85c7f86e2ef*****</AppId>
        <UpdateTime>1562587235588</UpdateTime>
        <AppName>app1</AppName>
        <TemplateId>wct-5d1eca8dd56beb722b7*****</TemplateId>
        <StackName>Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903</StackName>
    </ConfigTemplate>
    <Message>success</Message>
    <RequestId>733F3B46-0875-437A-9A8E-9549A0C*****</RequestId>
    <Code>OK</Code>
</UpdateConfigTemplateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"10C22D0D-C353-4535-89A9-FAB5017*****",
	"ConfigTemplate":{
		"TemplateName":"new-template-name",
		"StackId":"ws-6c937c98a9c0296d0c48*****",
		"CreateTime":1562299021581,
		"AppId":"wa-5d1d9d8c85c7f86e2ef*****",
		"UpdateTime":1562587235328,
		"AppName":"app1",
		"StackName":"Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903",
		"TemplateId":"wct-5d1eca8dd56beb722b7*****"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|TemplateNotExists|An error occurred while updating the configuration. No corresponding configuration template instance was found.|更新配置失败，没有找到相应的配置模版实例。|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|StackContainsNoConfigOption|An error occurred while modifying the configuration. The corresponding software stack does not contain any configuration items.|配置变更失败，对应的软件栈不包含任何的配置项。|
|404|ConfigOptionNotExists|An error occurred while updating the configuration. The system did not locate the configuration item declared by the key.|更新配置失败，没能找到对应的 key 所声明的配置项。|
|400|ChangingAReadonlyConfig|An error occurred while modifying the configuration. You cannot modify a read-only configuration.|更新配置失败，您不能对设置为只读的配置进行修改。|
|400|ConfigValueInvalid|An error occurred while resolving the configuration values. Please make sure the value type and constraints is consistent with the declared type. Types currently supported by WebPlus are: String, Integer, List, Boolean, Float, Json.|更新配置失败，对配置值的解析失败，请务必确保值的类型与约束与声明的类型保持一致，目前 WebPlus 配置支持的类型有：String, Integer, List, Boolean, Float, Json|
|404|AppPackageNotExists|An application deployment package is required to create or update a deployment environment. For the first time of using WebPlus, we recommend that you use a sample project.|创建/更新一个部署环境时，需要使用真实的应用部署包；如您是首次尝试使用 WebPlus，可以选择样例工程完成您的首次尝试。|
|400|AppPackageOwnedByOthers|The version of the application package used must be consistent with the application to which the environment belongs.|当创建/更新一个环境的版本信息时，所使用的应用部署包版本必须与环境所属的应用一致。|
|400|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|
|404|StackNotExists|The declared software stack information does not exist.|创建应用/更新应用环境时，所声明的软件栈信息不存在。|
|400|AppCategoryNotMatchWithStacks|The application type declared in the application does not match the type of the software stack. Please make sure that the types are consistent and then try again.|应用中所声明的应用类型与软件栈中的应用类型不匹配，需要确保两边一致后再进行重试。|
|400|TemplateUpdateFailed|An error occurred while updating the template. The template may have been deleted, or an error may have occurred in WebPlus.|配置模版更新失败，有可能模版已经被删除或 WebPlus 服务发生错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

