# DescribeChange {#doc_api_WebPlus_DescribeChange .reference}

调用DescribeChanges查询给定环境内所有变更信息或给定变更ID的变更信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeChange&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/changeInfo HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d245f7f1f773f090a0d\*\*\*\*|环境ID，将查询此环境内所有变更信息

 |
|ChangeId|String|否|wc-5d245f94f314934e2ab1\*\*\*\*|变更ID，将查询此变更ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Change| | |变更信息

 |
|ActionName|String|Apply|变更操作名称

 |
|ChangeAborted|Boolean|false|变更是否被中止

 |
|ChangeDescription|String|apply env we-5d39b8ba6786bd4b149\*\*\*\*\*|变更描述

 |
|ChangeFinished|Boolean|true|变更是否完成

 |
|ChangeId|String|wc-5d3a963d5802611c4dd\*\*\*\*\*|变更ID

 |
|ChangeMessage|String|changeMessage|变更消息

 |
|ChangeName|String|apply.env|变更名称

 |
|ChangePaused|Boolean|false|变更是否被暂停

 |
|ChangeSucceed|Boolean|true|变更是否成功

 |
|ChangeTimedout|Boolean|false|变更是否超时

 |
|CreateTime|Long|1562664852417|变更创建时间

 |
|CreateUsername|String|user1|变更创建者

 |
|EnvId|String|we-5d245f7f1f773f090a0\*\*\*\*\*|变更所属环境ID

 |
|FinishTime|Long|1562664854330|变更完成时间

 |
|UpdateTime|Long|1562664854381|变更最后更新时间

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|91AF2647-8A0B-47FE-8AD4-AE49AA79\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/changeInfo?ChangeId=wc-5d245f94f314934e2ab1****&ServiceCode=webx&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeChangeResponse>
    <Message>success</Message>
    <Change>
        <ChangeName>apply.env</ChangeName>
        <ActionName>Apply</ActionName>
        <ChangeAborted>false</ChangeAborted>
        <ChangeTimedout>false</ChangeTimedout>
        <UpdateTime>1564120665714</UpdateTime>
        <ChangeDescription>apply env we-5d39b8ba6786bd4b1495****</ChangeDescription>
        <EnvId>we-5d39b8ba6786bd4b1495****</EnvId>
        <ChangeSucceed>true</ChangeSucceed>
        <FinishTime>1564120665679</FinishTime>
        <CreateUsername>user1</CreateUsername>
        <CreateTime>1564120637891</CreateTime>
        <ChangeId>wc-5d3a963d5802611c4ddc****</ChangeId>
        <ChangeFinished>true</ChangeFinished>
        <ChangeMessage></ChangeMessage>
        <ChangePaused>false</ChangePaused>
    </Change>
    <RequestId>97CEF6FD-0266-4C15-8745-9325E2AB****</RequestId>
    <Code>OK</Code>
</DescribeChangeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Change":{
		"ChangeName":"apply.env",
		"ActionName":"Apply",
		"ChangeAborted":false,
		"ChangeTimedout":false,
		"UpdateTime":1564120665714,
		"ChangeDescription":"apply env we-5d39b8ba6786bd4b1495****",
		"EnvId":"we-5d39b8ba6786bd4b1495****",
		"ChangeSucceed":true,
		"FinishTime":1564120665679,
		"CreateUsername":"user1",
		"CreateTime":1564120637891,
		"ChangeId":"wc-5d3a963d5802611c4ddc****",
		"ChangeFinished":true,
		"ChangeMessage":"",
		"ChangePaused":false
	},
	"Message":"success",
	"RequestId":"150EA851-8DD9-4530-A3DF-5940B738****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|404|ChangeNotExists|The change record could not be found based on the change ID specified, please double confirm the resource is still exists.|无法根据所指定的变更 ID 找到变更记录，该记录可能被删除或传入的参数有误。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

