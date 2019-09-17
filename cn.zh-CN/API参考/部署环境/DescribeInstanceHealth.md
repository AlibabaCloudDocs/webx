# DescribeInstanceHealth {#doc_api_WebPlus_DescribeInstanceHealth .reference}

调用DescribeInstanceHealth查询一个给定ECS实例的健康状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeInstanceHealth&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/instance/health HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|i-wz9hwvnwm5tlv3u\*\*\*\*\*|id为实例ID，即instanceId，标识一个ECS实例

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|InstanceHealth| | |实例健康信息

 |
|AgentStatus|String|CONNECTED|代理连接状态

 |
|AppStatus|String|UNKOWN|应用状态

 |
|DisconnectedTime|Long|0|断连总时长

 |
|InstanceId|String|i-wz9hwvnwm5tlv3u\*\*\*\*\*|实例ID

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|FFBBC86A-2A15-4460-8B9C-BBC8E3F\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/instance/health?ServiceCode=webx&Id=i-wz9hwvnwm5tlv3u*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstanceHealthResponse>
    <InstanceHealth>
        <DisconnectedTime>0</DisconnectedTime>
        <InstanceId>i-wz9hwvnwm5tlv3u*****</InstanceId>
        <AgentStatus>CONNECTED</AgentStatus>
        <AppStatus>UNKOWN</AppStatus>
    </InstanceHealth>
    <Message>success</Message>
    <RequestId>6618008B-8BDF-4284-802B-E1DA40A*****</RequestId>
    <Code>OK</Code>
</DescribeInstanceHealthResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"FFBBC86A-2A15-4460-8B9C-BBC8E3F*****",
	"Code":"OK",
	"InstanceHealth":{
		"DisconnectedTime":0,
		"InstanceId":"i-wz9hwvnwm5tlv3u*****",
		"AgentStatus":"CONNECTED",
		"AppStatus":"UNKOWN"
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InstanceIdParamInvalid|The specified instance ID does not exist.|Instance ID 不存在。|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|404|InstanceNotExists|The specified instance does not exist according to the Instance ID declared. The specified instance may have been released or the parameter passed in is invalid.|根据所声明的实例 ID\(Instance Id\)，没有找到对应的实例，有可能所指定的实例已经被释放或参数传入有误。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

