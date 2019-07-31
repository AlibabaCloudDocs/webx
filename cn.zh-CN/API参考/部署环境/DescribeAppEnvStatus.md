# DescribeAppEnvStatus {#doc_api_WebPlus_DescribeAppEnvStatus .reference}

调用DescribeAppEnvStatus查询给定环境的状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeAppEnvStatus&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/appEnv/status HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d244085f314934e2ab15cd7|环境ID，将查询此环境的状态

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvStatus| | |环境状态信息

 |
|AbortingChange|Boolean|false|是否处于被终止状态

 |
|ApplyingChange|Boolean|false|是否正在对环境进行变更

 |
|ChangeBanner|String|Web+ is updating your deplpoyment environment.|变更的通知消息

 |
|EnvId|String|we-5d1af9c902470221ab7d6db9"|环境ID

 |
|EnvName|String|test1|环境名称

 |
|EnvStatus|String|RUNNING|环境运行状态

 |
|InstanceAgentStatus| | |实例代理状态

 |
|ConnectedInstances|Integer|0|已连接的实例个数

 |
|DisconnectedInstances|Integer|0|已断开连接的实例个数

 |
|InstanceAppStatus| | |实例应用健康状态状态

 |
|HealthyInstances|Integer|0|健康实例应用的个数

 |
|StoppedInstances|Integer|0|停止的实例应用个数

 |
|UnhealthyInstances|Integer|0|不健康的实例应用个数

 |
|UnknownInstances|Integer|0|位置状态的实例应用个数

 |
|LastEnvStatus|String|INITIALIZING|环境的上次状态

 |
|LatestChangeId|String|wc-5d3bb06a970b3f2e2a87c756"|环境上次变更的变更ID

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|3CE38930-5A6A-4F7E-A6AD-DBF0EDE5CE6C|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/status?ServiceCode=webx&Id=we-5d244085f314934e2ab15cd7&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAppEnvStatusResponse>
    <EnvStatus>
        <EnvStatus>RUNNING</EnvStatus>
        <AbortingChange>false</AbortingChange>
        <ChangeBanner>Web+ is trying to recover your deployment environment</ChangeBanner>
        <LatestChangeId>wc-5d3bb06a970b3f2e2a87c756</LatestChangeId>
        <LastEnvStatus>INITIALIZING</LastEnvStatus>
        <EnvName>xianbin-test-env</EnvName>
        <EnvId>we-5d1af9c902470221ab7d6db9</EnvId>
        <ApplyingChange>false</ApplyingChange>
        <InstanceAgentStatus>
            <DisconnectedInstances>0</DisconnectedInstances>
            <ConnectedInstances>0</ConnectedInstances>
        </InstanceAgentStatus>
        <InstanceAppStatus>
            <UnhealthyInstances>0</UnhealthyInstances>
            <StoppedInstances>0</StoppedInstances>
            <HealthyInstances>0</HealthyInstances>
            <UnknownInstances>0</UnknownInstances>
        </InstanceAppStatus>
    </EnvStatus>
    <Message>success</Message>
    <RequestId>F1D5FD22-87AC-483A-9310-4F7C6FB6ECC5</RequestId>
    <Code>OK</Code>
</DescribeAppEnvStatusResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"EnvStatus":{
		"EnvStatus":"RUNNING",
		"AbortingChange":false,
		"LastEnvStatus":"INITIALIZING",
		"ChangeBanner":"Web+ is trying to recover your deployment environment",
		"LatestChangeId":"wc-5d3bb06a970b3f2e2a87c756",
		"EnvName":"xianbin-test-env",
		"EnvId":"we-5d1af9c902470221ab7d6db9",
		"ApplyingChange":false,
		"InstanceAgentStatus":{
			"DisconnectedInstances":0,
			"ConnectedInstances":0
		},
		"InstanceAppStatus":{
			"UnhealthyInstances":0,
			"StoppedInstances":0,
			"HealthyInstances":0,
			"UnknownInstances":0
		}
	},
	"Message":"success",
	"RequestId":"30C31B90-F42F-4A17-9EE8-5CB5D690CB37",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

