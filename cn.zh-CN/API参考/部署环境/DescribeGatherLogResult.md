# DescribeGatherLogResult {#doc_api_WebPlus_DescribeGatherLogResult .reference}

调用DescribeGatherLogResult查询一个收集日志的变更信息。

**说明：** 只能查询收集日志对应的变更信息

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeGatherLogResult&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/appEnv/gatherLog HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChangeId|String|否|wc-5d412db056fd7c14ac9\*\*\*\*\*|变更ID，将查询此变更对应的日志收集信息

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|GatherLogResult| | |日志收集结果信息

 |
|Change| | |变更信息

 |
|ActionName|String|GatherLog|变更动作名称

 |
|ChangeAborted|Boolean|false|变更是否被终止

 |
|ChangeDescription|String|"gather logs of env we-5d3eaaea2977ca5251e\*\*\*\*\* on \[\\"\{\\\\\\"targetInstances\\\\\\":\\\\\\"i-wz94zz7mx8kt5kz\*\*\*\*\*\\\\\\"\}\\"\]|变更描述信息

 |
|ChangeFinished|Boolean|true|变更是否完成

 |
|ChangeId|String|wc-5d412db056fd7c14ac9\*\*\*\*\*|变更ID

 |
|ChangeMessage|String|""|变更信息

 |
|ChangeName|String|gather.log|变更名称

 |
|ChangePaused|Boolean|false|变更是否被停止

 |
|ChangeSucceeded|Boolean|true|变更是否成功

 |
|ChangeTimedout|Boolean|false|变更是否超时

 |
|CreateTime|Long|1564552624114|变更开始时间

 |
|CreateUsername|String|user1|变更创建者

 |
|EnvId|String|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID

 |
|FinishTime|Long|1564552624564|变更结束时间

 |
|UpdateTime|Long|1564552624600|上次更新时间

 |
|InstanceResults| | |实例结果信息

 |
|InstanceId|String|""|实例ID

 |
|StorageKey|String|""|存储key

 |
|TaskMessage|String|""|任务消息

 |
|TaskSucceeded|Boolean|true|任务是否完成

 |
|LogPath|String|/home/admin/app/webplus-app.log|日志路径

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|76A821B7-A376-47C5-956C-34827EF\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
GET /pop/v1/wam/appEnv/gatherLog HTTP/1.1
公共请求头
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeGatherLogResultResponse>
    <Message>success</Message>
    <RequestId>C3D45688-AD84-420D-9CF3-5650B49*****</RequestId>
    <GatherLogResult>
        <InstanceResults></InstanceResults>
        <Change>
            <ChangeName>gather.log</ChangeName>
            <ActionName>GatherLog</ActionName>
            <ChangeAborted>false</ChangeAborted>
            <ChangeTimedout>false</ChangeTimedout>
            <UpdateTime>1564552624600</UpdateTime>
            <ChangeDescription>gather logs of env we-5d3eaaea2977ca5251e***** on ["{\"targetInstances\":\"i-wz94zz7mx8kt5kz*****\"}"]</ChangeDescription>
            <EnvId>we-5d3eaaea2977ca5251e*****</EnvId>
            <FinishTime>1564552624564</FinishTime>
            <CreateUsername>user1</CreateUsername>
            <ChangeSucceeded>true</ChangeSucceeded>
            <CreateTime>1564552624114</CreateTime>
            <ChangeId>wc-5d412db056fd7c14ac9*****</ChangeId>
            <ChangeFinished>true</ChangeFinished>
            <ChangeMessage></ChangeMessage>
            <ChangePaused>false</ChangePaused>
        </Change>
        <LogPath>/home/admin/app/webplus-app.log</LogPath>
    </GatherLogResult>
    <Code>OK</Code>
</DescribeGatherLogResultResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"76A821B7-A376-47C5-956C-34827EF*****",
	"GatherLogResult":{
		"InstanceResults":{
			"InstanceResult":[]
		},
		"Change":{
			"ChangeName":"gather.log",
			"ActionName":"GatherLog",
			"ChangeAborted":false,
			"ChangeTimedout":false,
			"UpdateTime":1564552624600,
			"ChangeDescription":"gather logs of env we-5d3eaaea2977ca5251e***** on [\"{\\\"targetInstances\\\":\\\"i-wz94zz7mx8kt5kz*****\\\"}\"]",
			"EnvId":"we-5d3eaaea2977ca5251e*****",
			"FinishTime":1564552624564,
			"CreateUsername":"user1",
			"ChangeSucceeded":true,
			"CreateTime":1564552624114,
			"ChangeId":"wc-5d412db056fd7c14ac9*****",
			"ChangeFinished":true,
			"ChangeMessage":"",
			"ChangePaused":false
		},
		"LogPath":"/home/admin/app/webplus-app.log"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

