# DryRunTerminateAppEnv {#doc_api_WebPlus_DryRunTerminateAppEnv .reference}

调用DryRunTerminateAppEnv来模拟运行终止给定的部署环境。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DryRunTerminateAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/dryRunTerminate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID，将模拟运行终止此环境

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
|OperationDescription|String|Delete monitor group 7\*\*\*\*\*0|操作描述信息

 |
|OperationType|String|destroy|操作类型

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|D5B8AA8C-8F97-486E-8905-B812ED\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/dryRunTerminate&<公共请求头>

{
  "EnvId": "we-5d3eaaea2977ca5251e06*****"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DryRunTerminateAppEnvResponse>
    <Message>success</Message>
    <RequestId>D433AF27-DB06-4669-B28A-F7D*****2BFD</RequestId>
    <DryRunInfo>
        <Operations>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete monitor group 7*****0</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Scale in 1 ECS instance(s)</OperationDescription>
            </Operation>
            <Operation>
                <OperationType>destroy</OperationType>
                <OperationDescription>Delete security group sg-wz9hs5tvwl200wa*****</OperationDescription>
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
    </DryRunInfo>
    <Code>OK</Code>
</DryRunTerminateAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"D5B8AA8C-8F97-486E-8905-B812EDB*****",
	"DryRunInfo":{
		"Operations":{
			"Operation":[
				{
					"OperationType":"destroy",
					"OperationDescription":"Delete monitor group 7*****0"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Scale in 1 ECS instance(s)"
				},
				{
					"OperationType":"destroy",
					"OperationDescription":"Delete security group sg-wz9hs5tvwl200wa*****"
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

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

