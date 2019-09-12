# CreateAppEnv {#doc_api_WebPlus_CreateAppEnv .reference}

调用CreateAppEnv创建一个部署环境。

-   选择从已有环境或配置模板快速创建一个部署环境，使用两种方式创建环境时，将使用所选择环境或配置模板的部署包版本来部署新环境。
-   若不指定已有环境或配置模板，则必须指定技术栈ID和部署包版本ID。
-   若同时指定源环境ID，配置模板ID与技术栈ID中的多个参数，将依照源环境ID，配置模板ID，技术栈ID的优先级顺序来创建新环境。
-   此API被调用后若非模拟变更，则将返回此次创建的变更ID，可以使用此ID查询变更信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=CreateAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|否|wa-6c937c98a9c0296d0c48\*\*\*\*\*|应用ID

 |
|DryRun|Boolean|否|false|是否模拟变更

 -   若设定该参数为true，则不会创建变更，而是输出创建环境的操作步骤；否则会创建环境，并输出变更ID
    -   默认为false

 |
|EnvDescription|String|否|this is an env|环境描述信息

 |
|EnvName|String|否|envTest|环境名称

 |
|OptionSettings|String|否|\[\{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"\}, \{"path":"application.option", "name":"port","value":"8081"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|PkgVersionId|String|否|wp-6c937c98a9c0296d0c48\*\*\*\*\*|部署包版本ID

 |
|ProfileName|String|否|HighAvailability|初始化配置类型，可选以下值：

 -   `HighAvailability`：高可用，该配置会将实例数设置为2，同时启用公网SLB
-   `StandAlone`：低成本，该配置会将实例数设置为1

 |
|SourceEnvId|String|否|we-6c937c98a9c0296d0c48\*\*\*\*\*|源环境ID，新创建的环境将克隆此环境的技术栈，配置项和部署包版本。

 |
|StackId|String|否|ws-6c937c98a9c0296d0c48\*\*\*\*\*|环境使用的技术栈ID，若指定了源环境ID或配置模板ID，此参数将被忽略，否则必须指定此参数

 |
|TemplateId|String|否|wct-5d1c0a5d913567334af\*\*\*\*\*|源模版ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChangeDetail| | |环境变更信息

 |
|ChangeId|String|wc-5d3e71642977ca5251e\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|Operations| | |变更操作列表

 |
|Operation| | |变更操作列表

 |
|OperationDescription|String|Bind to VSwitch vsw-wz9gfawx1vxkimtj\*\*\*\*\*|操作描述信息

 |
|OperationType|String|create|操作类型

 |
|StartTime|String|1562666697684|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|8D69F3C4-EA43-49D5-875A-0893BF5\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv?<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateAppEnvResponse>
    <Message>success</Message>
    <RequestId>3E85CF06-071C-4A90-B7A1-2ACBA56*****</RequestId>
    <EnvChangeDetail>
        <Operations>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Bind to VPC vpc-wz9e6y22o3o91nuy*****</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Bind to VSwitch vsw-wz9gfawx1vxkimtj*****</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Create security group</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>update</OperationType>
                <OperationDescription>Update ESS scaling group</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-*****.small,ecs.*****.small,ecs.*****.tiny,ecs.*****.large (Creating resources may incur charges, please see //www.aliyun.com/price/product ?#/ecs/detail ECS Pricing&gt;</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Setup platform services on ECS instance(s)</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>create</OperationType>
                <OperationDescription>Create monitor group</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>update</OperationType>
                <OperationDescription>Synchronous ECS instance(s) to monitor group</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>update</OperationType>
                <OperationDescription>Change application on the instance(s)</OperationDescription>
            </Operation>
        </Operations>
    </EnvChangeDetail>
    <Code>OK</Code>
</CreateAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"607E6D37-6037-48FD-A89E-A57C584*****",
	"EnvChangeDetail":{
		"Operations":{
			"Operation":[
				{
					"OperationType":"create",
					"OperationDescription":"Bind to VPC vpc-wz9e6y22o3o91nuy*****"
				},
				{
					"OperationType":"create",
					"OperationDescription":"Bind to VSwitch vsw-wz9gfawx1vxkimtj*****"
				},
				{
					"OperationType":"create",
					"OperationDescription":"Create security group"
				},
				{
					"OperationType":"update",
					"OperationDescription":"Update ESS scaling group"
				},
				{
					"OperationType":"create",
					"OperationDescription":"Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-*****.small,ecs.*****.small,ecs.n1.tiny,ecs.*****.large (<b>Creating resources may incur charges, please see <a href=\"//www.aliyun.com/price/product ?#/ecs/detail\" target=\"_blank\">ECS Pricing</a></b>)"
				},
				{
					"OperationType":"create",
					"OperationDescription":"Setup platform services on ECS instance(s)"
				},
				{
					"OperationType":"create",
					"OperationDescription":"Create monitor group"
				},
				{
					"OperationType":"update",
					"OperationDescription":"Synchronous ECS instance(s) to monitor group"
				},
				{
					"OperationType":"update",
					"OperationDescription":"Change application on the instance(s)"
				}
			]
		}
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|500|EnvCreateFailed|An error occurred while creating an environment.|创建环境失败，在往插入记录时遇到未知错误。|
|500|OSSDisabled|You have not activated the OSS service and cannot use the WebPlus service. Please go to the OSS console \(https://oss.console.aliyun.com\) to activate OSS and try again.|您没有开通 OSS 服务，不能使用 WebPlus 服务，请前往 OSS 控制台\(https://oss.console.aliyun.com\) 开通后重试。|
|500|OSSApiCallFailed|When initializing applications, updating configurations, or destroying applications, WebPlus attempts to communicate with OSS through API communication. An OSS service throw error occurred. The bucket or the file does not exist.|在初始化应用、更新配置、以及销毁应用时，WebPlus 尝试与 OSS 进行 API 通信出现 OSS 服务抛出的异常，如 bucket 不存在、文件不存在等。|
|500|StackNotExists|The declared software stack information does not exist.|创建应用/更新应用环境时，所声明的软件栈信息不存在。|
|500|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|
|500|AppCategoryNotMatchWithStacks|The application type declared in the application does not match the type of the software stack. Please make sure that the types are consistent and then try again.|应用中所声明的应用类型与软件栈中的应用类型不匹配，需要确保两边一致后再进行重试。|
|500|StackContainsNoConfigOption|An error occurred while modifying the configuration. The corresponding software stack does not contain any configuration items.|配置变更失败，对应的软件栈不包含任何的配置项。|
|404|ConfigOptionNotExists|An error occurred while updating the configuration. The system did not locate the configuration item declared by the key.|更新配置失败，没能找到对应的 key 所声明的配置项。|
|500|ChangingAReadonlyConfig|An error occurred while modifying the configuration. You cannot modify a read-only configuration.|更新配置失败，您不能对设置为只读的配置进行修改。|
|500|ConfigValueInvalid|An error occurred while resolving the configuration values. Please make sure the value type and constraints is consistent with the declared type. Types currently supported by WebPlus are: String, Integer, List, Boolean, Float, Json.|更新配置失败，对配置值的解析失败，请务必确保值的类型与约束与声明的类型保持一致，目前 WebPlus 配置支持的类型有：String, Integer, List, Boolean, Float, Json|
|500|AppPackageNotExists|An application deployment package is required to create or update a deployment environment. For the first time of using WebPlus, we recommend that you use a sample project.|创建/更新一个部署环境时，需要使用真实的应用部署包；如您是首次尝试使用 WebPlus，可以选择样例工程完成您的首次尝试。|
|500|AppPackageOwnedByOthers|The version of the deployment package used must be consistent with the application to which the environment belongs.|当创建/更新一个环境的版本信息时，所使用的应用部署包版本必须与环境所属的应用一致。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

