# TerminateAppEnv {#doc_api_WebPlus_TerminateAppEnv .reference}

调用TerminateAppEnv来终止一个环境。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=TerminateAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/terminate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|DryRun|String|否|true|是否模拟变更

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
|OperationDescription|String|Delete monitor group 78\*\*\*\*\*|变更操作描述信息

 |
|OperationType|String|destroy|操作类型

 |
|StartTime|String|1564373348658|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|393D5428-E693-4063-9C59-1D5393E\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/terminate?ServiceCode=webx&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<TerminateAppEnvResponse>
    <Message>success</Message>
    <RequestId>1DCDA97A-5F5E-4DEC-85C7-9F2EE02*****</RequestId>
    <EnvChangeDetail>
        <Operations>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete monitor group 78*****</OperationDescription>
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
</TerminateAppEnvResponse>
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
|403|StatusNotAllowedTerminated|A terminate action cannot be performed on an environment that has already terminated.|不能对已经终止的环境执行应用终止操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

