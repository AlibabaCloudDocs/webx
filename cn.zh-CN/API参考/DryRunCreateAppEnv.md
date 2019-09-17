# DryRunCreateAppEnv {#doc_api_WebPlus_DryRunCreateAppEnv .reference}

调用DryRunCreateAppEnv来模拟创建应用部署环境。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DryRunCreateAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/dryRunCreate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|OptionSettings|String|否|\[\{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"\}, \{"path":"application.option", "name":"port","value":"8081"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|ProfileName|String|否|HighAvailability|初始化配置类型，可选以下值：

 -   `HighAvailability`：高可用，该配置会将实例数设置为2，同时启用公网SLB
-   `StandAlone`：低成本，该配置会将实例数设置为1

 |
|SourceEnvId|String|否|we-5d3eaaea2977ca5251e\*\*\*\*\*|源环境ID

 |
|StackId|String|否|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈ID

 |
|TemplateId|String|否|wct-5d1eca8dd56beb722b7\*\*\*\*\*|模板ID，从此配置模板创建环境

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|DryRunInfo| | |模拟运行信息

 |
|Operations| | |操作列表

 |
|OperationDescription|String|Bind to VPC vpc-wz9e6y22o3o91nuy\*\*\*\*\*|操作描述信息

 |
|OperationType|String|create|操作类型

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|E3EE84E8-52CC-4A76-850E-4CCFD9\*\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/dryRunCreate&公共请求头
{
  "StackId": "ws-6c937c98a9c0296d0c48*****",
  "OptionSettings":"[{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"},     {"path":"application.option", "name":"port","value":"8081"}]",
  "ProfileName":"HighAvailability",
  "SourceEnvId":”we-5d3eaaea2977ca5251e*****“,
  "TemplateId":"wct-5d1eca8dd56beb722b7*****"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DryRunCreateAppEnvResponse>
    <Message>success</Message>
    <RequestId>C1AE1099-08A5-4BA4-85AF-BE30CD******</RequestId>
    <DryRunInfo>
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
                <OperationDescription>"Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-*****.small,ecs.*****.small,ecs.*****.tiny,ecs.*****.large (Creating resources may incur charges, please see "//www.aliyun.com/price/product ?#/ecs/detail ECS Pricing"</OperationDescription>
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
    </DryRunInfo>
    <Code>OK</Code>
</DryRunCreateAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"E3EE84E8-52CC-4A76-850E-4CCFD94*****",
	"DryRunInfo":{
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
					"OperationDescription":"Create 1 ECS instances and create instances with priority using the following instance specifications: ecs.t5-*****.small,ecs.*****.small,ecs.*****.tiny,ecs.*****.large (<b>Creating resources may incur charges, please see <a href=\"//www.aliyun.com/price/product ?#/ecs/detail\" target=\"_blank\">ECS Pricing</a></b>)"
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

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

