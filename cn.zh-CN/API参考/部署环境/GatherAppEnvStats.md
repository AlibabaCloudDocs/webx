# GatherAppEnvStats {#doc_api_WebPlus_GatherAppEnvStats .reference}

调用GatherAppEnvStats来收集一个部署环境中的诊断信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=GatherAppEnvStats&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/gatherStats HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID，将收集此环境中指定实例的诊断信息

 |
|TargetInstances|String|否|\["i-wz94zz7mx8kt5kz\*\*\*\*\*"\]|实例ID列表，将收集此列表中指定实例的诊断信息

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChange| | |变更信息

 |
|ChangeId|String|wc-5d4103a856fd7c14ac9\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID

 |
|StartTime|String|1564541864384|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|BDA78DBA-7D10-4DDB-B73F-8357EB8\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/gatherStats&公共请求头
{
  "EnvId": "we-5d3eaaea2977ca5251e*****"，
  "TargetInstances":"["i-wz94zz7mx8kt5kz*****"]"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GatherAppEnvStatsResponse>
      <Message>success</Message>
      <EnvChange>
            <EnvId>we-5d39b8ba6786bd4b1495****</EnvId>
            <StartTime>1564541276614</StartTime>
            <ChangeId>wc-5d3a963d5802611c4ddc****</ChangeId>
      </EnvChange>
      <RequestId>97CEF6FD-0266-4C15-8745-9325E2AB****</RequestId>
      <Code>OK</Code>
</GatherAppEnvStatsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"BDA78DBA-7D10-4DDB-B73F-8357EB8*****",
	"EnvChange":{
		"EnvId":"we-5d3eaaea2977ca5251e*****",
		"ChangeId":"wc-5d4103a856fd7c14ac9*****",
		"StartTime":1564541864384
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

