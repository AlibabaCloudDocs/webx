# DescribeGatherStatsResult {#doc_api_WebPlus_DescribeGatherStatsResult .reference}

调用DescribeGatherStatsResult查询一个收集诊断的变更信息。

**说明：** 只能查询收集诊断信息对应的变更信息

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeGatherStatsResult&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/appEnv/gatherStats HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChangeId|String|否|wc-5d4134b956fd7c14ac91\*\*\*\*\*|变更ID，将查询此变更ID对应的诊断结果信息

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|GatherStatsResult| | |日志收集结果信息

 |
|Change| | |变更信息

 |
|ActionName|String|GatherStats|变更动作名称

 |
|ChangeAborted|Boolean|false|变更是否被终止

 |
|ChangeDescription|String|gather stats of env we-5d3eaaea2977ca5251e\*\*\*\*\* on \[\\"\{\\\\\\"targetInstances\\\\\\":\\\\\\"i-wz94zz7mx8kt5kz\*\*\*\*\*\\\\\\"\}\\"\]|变更描述信息

 |
|ChangeFinished|Boolean|true|变更是否完成

 |
|ChangeId|String|wc-5d4134b956fd7c14ac9\*\*\*\*\*|变更ID

 |
|ChangeMessage|String|""|变更消息

 |
|ChangeName|String|gather.stats|变更名称

 |
|ChangePaused|Boolean|false|变更是否被停止

 |
|ChangeSucceeded|Boolean|true|变更是否成功

 |
|ChangeTimedout|Boolean|false|变更是否超时

 |
|CreateTime|Long|1564554425575|变更开始时间

 |
|CreateUsername|String|user1|变更创建者

 |
|EnvId|String|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID

 |
|FinishTime|Long|1564554426063|变更完成时间

 |
|UpdateTime|Long|1564554426111|上次更新时间

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
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|D208107C-B729-4C92-80EE-7257131\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/gatherStats?ChangeId=wc-5d4134b956fd7c14ac9*****&公共请求头

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeGatherStatsResultResponse>
    <Message>success</Message>
    <RequestId>344B98E9-269C-47D6-B55A-1CB268A*****</RequestId>
    <GatherStatsResult>
        <InstanceResults></InstanceResults>
        <Change>
            <ChangeName>gather.stats</ChangeName>
            <ActionName>GatherStats</ActionName>
            <ChangeAborted>false</ChangeAborted>
            <ChangeTimedout>false</ChangeTimedout>
            <UpdateTime>1564554426111</UpdateTime>
            <ChangeDescription>gather stats of env we-5d3eaaea2977ca5251e***** on ["{\"targetInstances\":\"i-wz94zz7mx8kt5kz*****\"}"]</ChangeDescription>
            <EnvId>we-5d3eaaea2977ca5251e*****</EnvId>
            <FinishTime>1564554426063</FinishTime>
            <CreateUsername>user1</CreateUsername>
            <ChangeSucceeded>true</ChangeSucceeded>
            <CreateTime>1564554425575</CreateTime>
            <ChangeId>wc-5d4134b956fd7c14ac9*****</ChangeId>
            <ChangeFinished>true</ChangeFinished>
            <ChangeMessage></ChangeMessage>
            <ChangePaused>false</ChangePaused>
        </Change>
    </GatherStatsResult>
    <Code>OK</Code>
</DescribeGatherStatsResultResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"GatherStatsResult":{
		"InstanceResults":{
			"InstanceResult":[]
		},
		"Change":{
			"ChangeName":"gather.stats",
			"ActionName":"GatherStats",
			"ChangeAborted":false,
			"ChangeTimedout":false,
			"UpdateTime":1564554426111,
			"ChangeDescription":"gather stats of env we-5d3eaaea2977ca5251e***** on [\"{\\\"targetInstances\\\":\\\"i-wz94zz7mx8kt5kz*****\\\"}\"]",
			"EnvId":"we-5d3eaaea2977ca5251e*****",
			"FinishTime":1564554426063,
			"CreateUsername":"user1",
			"ChangeSucceeded":true,
			"CreateTime":1564554425575,
			"ChangeId":"wc-5d4134b956fd7c14ac9*****",
			"ChangeFinished":true,
			"ChangeMessage":"",
			"ChangePaused":false
		}
	},
	"RequestId":"D208107C-B729-4C92-80EE-7257131*****",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

