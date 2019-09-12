# UpdateAppEnv {#doc_api_WebPlus_UpdateAppEnv .reference}

调用此API更新一个部署环境。

-   无法通过修改技术栈ID来修改环境的技术栈类型。
-   更新环境所使用的部署包版本必须与环境属于同一个应用。
-   此API被调用后若非模拟变更，则将返回此次创建的变更ID，可以使用此ID查询变更信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=UpdateAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
PUT /pop/v1/wam/appEnv HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d39b8ba6786bd4b149\*\*\*\*\*|要更新的环境ID

 |
|DryRun|Boolean|否|false|是否模拟变更

 -   若设定该参数为true，则不会创建变更，而是输出创建环境的操作步骤；否则会创建环境，并输出变更ID
    -   默认为false

 |
|EnvDescription|String|否|This is an env.|环境描述信息

 |
|ExtraProperties|String|否|\{"Keypair":"testKey"\}|本次变更的附加参数

 |
|OptionSettings|String|否|\[\{"path":"resources.slb.internet", "name":"enable","value":"true"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|PkgVersionId|String|否|wp-5d1c0a5d913567334af\*\*\*\*\*|部署包版本ID

 |
|StackId|String|否|ws-6c937c98a9c0296d0c48\*\*\*\*\*|环境所使用的技术栈ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChangeDetail| | |环境变更信息

 |
|ChangeId|String|wc-5d3bb06a970b3f2e2a8\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|Operations| | |变更操作

 |
|Operation| | |变更操作

 |
|OperationDescription|String|Unbind VSwitch\(es\) vsw-wz9gfawx1vxkimtj\*\*\*\*\*|变更操作

 |
|OperationType|String|destroy|操作类型

 |
|StartTime|String|1562666600768|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|8D69F3C4-EA43-49D5-875A-0893BF5\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv&<公共请求参数>
{
  "EnvId":"we-5d22bc1a6f48e5478fd*****"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateAppEnvResponse>
    <Message>success</Message>
    <RequestId>1DCDA97A-5F5E-4DEC-85C7-9F2EE02*****</RequestId>
    <EnvChangeDetail>
        <Operations>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete monitor group *****03</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete security group sg-wz97khuqdfkclpr*****</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete scaling group on ESS</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Unbind VSwitch(es) vsw-wz9gfawx1vxkimtj*****</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Unbind VPC vpc-wz9e6y22o3o91nuy*****</OperationDescription>
            </Operation>
        </Operations>
    </EnvChangeDetail>
    <Code>OK</Code>
</UpdateAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"393D5428-E693-4063-9C59-1D5393E*****",
	"EnvChangeDetail":{
		"Operations":{
			"Operation":[
				{
					"OperationType":"destroy",
					"OperationDescription":"Delete monitor group 78*****"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Delete security group sg-wz97khuqdfkclpr*****"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Delete scaling group on ESS"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Unbind VSwitch(es) vsw-wz9gfawx1vxkimtj*****"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Unbind VPC vpc-wz9e6y22o3o91nuy*****"
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
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|404|ConfigOptionNotExists|An error occurred while updating the configuration. The system did not locate the configuration item declared by the key.|更新配置失败，没能找到对应的 key 所声明的配置项。|
|400|ChangingAReadonlyConfig|An error occurred while modifying the configuration. You cannot modify a read-only configuration.|更新配置失败，您不能对设置为只读的配置进行修改。|
|403|VpcNotAllowedUpdate|You are not allowed to modify the VPC ID against an unterminated environment. Please terminate it before continuing this operation.|未终止的环境不允许修改 VPC ID，请先终止环境后再继续此项操作。|
|400|ConfigValueInvalid|An error occurred while resolving the configuration values. Please make sure the value type and constraints is consistent with the declared type. Types currently supported by WebPlus are: String, Integer, List, Boolean, Float, Json.|更新配置失败，对配置值的解析失败，请务必确保值的类型与约束与声明的类型保持一致，目前 WebPlus 配置支持的类型有：String, Integer, List, Boolean, Float, Json|
|400|AppPackageOwnedByOthers|The version of the application package used must be consistent with the application to which the environment belongs.|当创建/更新一个环境的版本信息时，所使用的应用部署包版本必须与环境所属的应用一致。|
|400|AppCategoryNotMatchWithStacks|The application type declared in the application does not match the type of the software stack. Please make sure that the types are consistent and then try again.|应用中所声明的应用类型与软件栈中的应用类型不匹配，需要确保两边一致后再进行重试。|
|400|EnvOnChanging|An error occurred while starting the change. Wait until the ongoing change is complete.|变更启动失败，原因是上一个变更正在进行，请等待上一次变更完成后再继续。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

