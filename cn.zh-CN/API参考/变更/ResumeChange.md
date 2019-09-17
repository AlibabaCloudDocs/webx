# ResumeChange {#doc_api_WebPlus_ResumeChange .reference}

调用ResumeChange来恢复一个被暂停的变更操作。

**说明：** 被恢复的变更必须是处于**已停止**状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=ResumeChange&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/change/resume HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChangeId|String|是|wc-5d3fabad56fd7c14ac9\*\*\*\*\*|变更ID，将恢复此变更操作

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChange| | |环境变更信息

 |
|ChangeId|String|wc-5d3fabad56fd7c14ac9\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|StartTime|String|1564453805573|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|F38283EF-B83B-47C0-992D-1DC450DE\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/change/resume&<公共请求头>
{
  "ChangeId": "wc-5d3fabad56fd7c14ac9*****"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ResumeChangeResponse>
    <Message>success</Message>
    <EnvChange>
        <EnvId>we-5d39b8ba6786bd4b149*****</EnvId>
        <StartTime>1564453805573</StartTime>
        <ChangeId>wc-5d3fabad56fd7c14ac9*****</ChangeId>
    </EnvChange>
    <RequestId>97CEF6FD-0266-4C15-8745-9325E2AB****</RequestId>
    <Code>OK</Code>
</ResumeChangeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"F38283EF-B83B-47C0-992D-1DC450DE****",
	"EnvChange":{
		"EnvId":"we-5d39b8ba6786bd4b149*****",
		"ChangeId":"wc-5d3fabad56fd7c14ac9*****",
		"StartTime":1564453805573
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

