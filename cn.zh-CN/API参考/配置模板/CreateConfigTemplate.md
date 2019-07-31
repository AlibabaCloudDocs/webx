# CreateConfigTemplate {#doc_api_WebPlus_CreateConfigTemplate .reference}

调用CreateConfigTemplate从一个原有环境来创建一个配置模板。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=CreateConfigTemplate&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/configTemplate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|否|wa-5d1d9d8c85c7f86e2efb\*\*\*\*|新建模板所在的应用ID

 |
|OptionSettings|String|否|\[\{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"\}, \{"path":"application.option", "name":"port","value":"8081"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|PkgVersionId|String|否|wp-5d1daece08350d1dd948\*\*\*\*|部署包版本ID

 |
|ProfileName|String|否|HighAvailability|初始化配置类型，可选以下值：

 -   `HighAvailability`：高可用，该配置会将实例数设置为2，同时启用公网SLB
-   `StandAlone`：低成本，该配置会将实例数设置为1

 |
|SourceEnvId|String|否|we-5d1dac8e08350d1dd948\*\*\*\*|源环境ID，指定用于创建模版配置的源环境

 |
|SourceTemplateId|String|否|wct-5d1ec2813c940d1bf45b\*\*\*\*|源配置模板的ID，将会以此模板来创建新的配置模板

 |
|StackId|String|否|ws-6c937c98a9c0296d0c482\*\*\*\*|技术栈ID

 |
|TemplateDescription|String|否|this is an new template|新建模版的描述

 |
|TemplateName|String|否|new-template-name|新建模板的名称

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|ConfigTemplate| | |配置模板信息

 |
|AppId|String|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID

 |
|AppName|String|app1|应用名称

 |
|CreateTime|Long|1562589211442|配置模板创建时间

 |
|PkgVersionId|String|wp-5d1daece08350d1dd94\*\*\*\*\*|部署包版本ID

 |
|PkgVersionLabel|String|20190726.135654|部署包版本标签

 |
|StackId|String|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈ID

 |
|StackName|String|Java 8 / Aliyun Linux 2.1903|技术栈名称

 |
|TemplateDescription|String|this is an new template|模板描述信息

 |
|TemplateId|String|wct-5d1ec866d56beb722b7\*\*\*\*\*|配置模板ID

 |
|TemplateName|String|new-template-name|配置模板名称

 |
|TemplateType|String|web|配置模板类型

 |
|UpdateTime|Long|1562298470970|上次更新时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|7C8AA286-14EA-4713-B81D-859BECF1\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/configTemplate?ServiceCode=webx&<公共请求参数>
{
   "TemplateName","new-template-name",
   "TemplateDescription","this is an new template",
   "AppId","wa-5d1d9d8c85c7f86e2efb****",
   "StackId","ws-6c937c98a9c0296d0c482****",
   "SourceTemplateId","wct-5d1ec2813c940d1bf45b****",
   "SourceEnvId","we-5d1dac8e08350d1dd948****",
   "ProfileName","HighAvailability",
   "PkgVersionId","wp-5d1daece08350d1dd948****",
   "OptionSettings","[{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"},     {"path":"application.option", "name":"port","value":"8081"}]",
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateConfigTemplateResponse>
      <ConfigTemplate>
            <TemplateName>new-template-name</TemplateName>
            <TemplateDescription>this is an new template</TemplateDescription>
            <Type>web</Type>
            <StackId>ws-6c937c98a9c0296d0c482****</StackId>
            <CreateTime>1562298470970</CreateTime>
            <AppId>wa-5d1d9d8c85c7f86e2efb****</AppId>
            <UpdateTime>1562298470970</UpdateTime>
            <AppName>app1</AppName>
            <TemplateId>wct-5d1ec866d56beb722b77****</TemplateId>
            <PkgVersionId>wp-5d1daece08350d1dd948****</PkgVersionId>
            <StackName>Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903</StackName>
      </ConfigTemplate>
      <Message>success</Message>
      <RequestId>7C8AA286-14EA-4713-B81D-859BECF1****</RequestId>
      <Code>OK</Code>
</CreateConfigTemplateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"02DE47B1-68AE-4F15-AC0B-94166D4F****",
	"ConfigTemplate":{
		"TemplateType":"web",
		"TemplateName":"template-name",
		"TemplateDescription":"this is an new template",
		"StackId":"ws-6c937c98a9c0296d0c482****",
		"CreateTime":1564384554840,
		"PkgVersionLabel":"20190726.135654",
		"AppId":"wa-5d1af9c802470221ab7d****",
		"UpdateTime":1564384554840,
		"AppName":"app1",
		"PkgVersionId":"wp-5d3a963b5802611c4ddc****",
		"StackName":"Java 8 / Aliyun Linux 2.1903",
		"TemplateId":"wct-5d3e9d2a2977ca5251e0****"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|
|400|DuplicatedTemplateName|An error occurred while generating an environment configuration template. The specified template name already exists in the application.|生成环境配置模版失败，在该应用下，您不能使用已经使用过的模版名称。|
|400|AppCategoryNotMatchWithStacks|The application type declared in the application does not match the type of the software stack. Please make sure that the types are consistent and then try again.|应用中所声明的应用类型与软件栈中的应用类型不匹配，需要确保两边一致后再进行重试。|
|404|StackNotExists|The declared software stack information does not exist.|创建应用/更新应用环境时，所声明的软件栈信息不存在。|
|400|StackContainsNoConfigOption|An error occurred while modifying the configuration. The corresponding software stack does not contain any configuration items.|配置变更失败，对应的软件栈不包含任何的配置项。|
|404|ConfigOptionNotExists|An error occurred while updating the configuration. The system did not locate the configuration item declared by the key.|更新配置失败，没能找到对应的 key 所声明的配置项。|
|400|ChangingAReadonlyConfig|An error occurred while modifying the configuration. You cannot modify a read-only configuration.|更新配置失败，您不能对设置为只读的配置进行修改。|
|400|ConfigValueInvalid|An error occurred while resolving the configuration values. Please make sure the value type and constraints is consistent with the declared type. Types currently supported by WebPlus are: String, Integer, List, Boolean, Float, Json.|更新配置失败，对配置值的解析失败，请务必确保值的类型与约束与声明的类型保持一致，目前 WebPlus 配置支持的类型有：String, Integer, List, Boolean, Float, Json|
|404|AppPackageNotExists|An application deployment package is required to create or update a deployment environment. For the first time of using WebPlus, we recommend that you use a sample project.|创建/更新一个部署环境时，需要使用真实的应用部署包；如您是首次尝试使用 WebPlus，可以选择样例工程完成您的首次尝试。|
|400|AppPackageOwnedByOthers|The version of the application package used must be consistent with the application to which the environment belongs.|当创建/更新一个环境的版本信息时，所使用的应用部署包版本必须与环境所属的应用一致。|
|400|ConfigParsingFailed|An error occurred while extracting the corresponding item from the configuration. Please check the configuration and try again.|从配置中抽取出对应项时，出现解析参数项的配置；请认真核对配置，修正后重试。|
|400|ProfileNameInvalid|The specified cluster type in the template is invalid. Valid values: Default, StandAlone, and HighAvailability.|启动模版的集群类型名称不合法，该枚举的取值范围为：Default, StandAlone, HighAvailability.|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

