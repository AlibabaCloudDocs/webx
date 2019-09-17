# RebuildAppEnv {#doc_api_WebPlus_RebuildAppEnv .reference}

调用RebuildAppEnv重建一个部署环境。

-   只能针对状态处于**已释放**和**异常**的环境执行停止操作。
-   此API被调用后若非模拟变更，则将返回此次创建的变更ID，可以使用此ID查询变更信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=RebuildAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/rebuild HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|DryRun|Boolean|否|true|是否模拟变更

 -   若设定该参数为true，则不会创建变更，而是输出创建环境的操作步骤；否则会创建环境，并输出变更ID
    -   默认为false

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
|OperationDescription|String|Change application on the instance\(s\)|变更操作描述

 |
|OperationType|String|update|变更操作类型

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

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/rebuild?Id=we-5d22bc1a6f48e5478fd*****&<公共请求参数>
{
  "EnvId":"we-5d39b8ba6786bd4b149*****",
  "DryRun":true,
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RebuildAppEnvResponse>
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
                <OperationDescription>Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-****.small,ecs.***.small,ecs.***,ecs.g5.large Creating resources may incur charges, please see //www.aliyun.com/price/product ?#/ecs/detail ECS Pricing</OperationDescription>
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
</RebuildAppEnvResponse>
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
					"OperationDescription":"Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-lc1*1.*****,ecs.***.small,ecs.****.tiny,ecs.***.large (<b>Creating resources may incur charges, please see <a href=\"//www.aliyun.com/price/product ?#/ecs/detail\" target=\"_blank\">ECS Pricing</a></b>)"
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
|403|StatusNotAllowedRebuild|You can only rebuild a terminated environment or an environment that failed to be rebuilt.|应用环境重建只能针对两种状态进行：已终止或上次执行失败。其他状态不允许重建的操作。|
|400|EnvOnChanging|An error occurred while starting the change. Wait until the ongoing change is complete.|变更启动失败，原因是上一个变更正在进行，请等待上一次变更完成后再继续。|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|OSSDisabled|You have not activated the OSS service and cannot use the WebPlus service. Please go to the OSS console \(https://oss.console.aliyun.com\) to activate OSS and try again.|您没有开通 OSS 服务，不能使用 WebPlus 服务，请前往 OSS 控制台\(https://oss.console.aliyun.com\) 开通后重试。|
|400|OSSApiCallFailed|When initializing applications, updating configurations, or destroying applications, WebPlus attempts to communicate with OSS through API communication. An OSS service throw error occurred. The bucket or the file does not exist.|在初始化应用、更新配置、以及销毁应用时，WebPlus 尝试与 OSS 进行 API 通信出现 OSS 服务抛出的异常，如 bucket 不存在、文件不存在等。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

