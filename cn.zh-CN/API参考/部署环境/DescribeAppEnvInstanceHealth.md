# DescribeAppEnvInstanceHealth {#doc_api_WebPlus_DescribeAppEnvInstanceHealth .reference}

调用DescribeAppEnvInstanceHealth查询一个环境内所有ECS实例的健康状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeAppEnvInstanceHealth&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/appEnv/instanceHealth HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d244085f314934e2ab\*\*\*\*\*|环境ID，将查询此环境内所有实例的健康状态

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvInstanceHealth| | |实例健康状态查询结果

 |
|EnvId|String|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID

 |
|EnvName|String|test-env|环境名称

 |
|InstanceHealthList| | |实例健康列表

 |
|AgentStatus|String|CONNECTED|代理连接状态

 |
|AppStatus|String|HEALTHY|应用状态

 |
|DisconnectedTime|String|0|断连时长

 |
|InstanceId|String|i-wz95ehd0129c8vv\*\*\*\*\*|ECS实例ID

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|C8E457BD-0E3D-4EF0-AA1F-A36FE27\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/instanceHealth?ServiceCode=webx&EnvId=we-5d244085f314934e2ab*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAppEnvInstanceHealthResponse>
    <Message>success</Message>
    <RequestId>C99E58A1-5D86-4D50-B443-E41EEE1*****</RequestId>
    <EnvInstanceHealth>
        <EnvName>test-env</EnvName>
        <InstanceHealthList>
            <InstanceHealth>
                <DisconnectedTime>0</DisconnectedTime>
                <InstanceId>i-wz95ehd0129c8vv*****</InstanceId>
                <AgentStatus>CONNECTED</AgentStatus>
                <AppStatus>HEALTHY</AppStatus>
            </InstanceHealth>
        </InstanceHealthList>
        <EnvId>we-5d3eaaea2977ca5251e*****</EnvId>
    </EnvInstanceHealth>
    <Code>OK</Code>
</DescribeAppEnvInstanceHealthResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"C8E457BD-0E3D-4EF0-AA1F-A36FE27*****",
	"EnvInstanceHealth":{
		"EnvName":"test-env",
		"InstanceHealthList":{
			"InstanceHealth":[
				{
					"DisconnectedTime":0,
					"InstanceId":"i-wz95ehd0129c8vv*****",
					"AgentStatus":"CONNECTED",
					"AppStatus":"HEALTHY"
				}
			]
		},
		"EnvId":"we-5d3eaaea2977ca5251e*****"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

