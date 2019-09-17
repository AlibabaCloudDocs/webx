# DescribeEvents {#doc_api_WebPlus_DescribeEvents .reference}

调用DescribeEvents查询事件。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeEvents&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/event HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d1dac8e08350d1dd94\*\*\*\*\*|环境ID，将查询此环境上的事件

 |
|ChangeId|String|否|wc-d2eeaaa1405481bdd8cb92c\*\*\*\*\*|变更ID

 |
|EndTime|Long|否|1562225909800|查询事件的结束时间戳

 |
|LastChangeEvents|Boolean|否|true|最近更新事件

 |
|PageNumber|Integer|否|10|查询页面数量

 |
|PageSize|Integer|否|1|查询页面大小

 |
|ReverseByTimestamp|Boolean|否|true|返回列表是否按时间戳倒序排序

 |
|StartTime|Long|否|1562225800000|查询事件的开始时间戳

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Events| | |事件列表

 |
|AppId|String|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID

 |
|EnvId|String|we-5d1dac8e08350d1dd94\*\*\*\*\*|环境ID

 |
|EnventName|String|envName|事件名称

 |
|EventId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|事件ID

 |
|EventLevel|String|INFO|事件等级

 |
|EventMessage|String|Change wc-5d39b8bc6786bd4b149\*\*\*\*\* finish successfully, taking 108 seconds<|事件消息

 |
|EventTimestamp|Long|1564064041112|事件时间戳

 |
|MsgCode|String|webx.wam.change.vpc.create.success|消息代码

 |
|MsgParams| |we-5d1dac8e08350d1dd94\*\*\*\*\*|消息参数

 |
|ObjectAttrs| | |对象属性列表

 |
|AttributeName|String|""|属性名称

 |
|AttributeValue|String|""|属性值

 |
|ObjectId|String|vpc-wz9e6y22o3o91nuy\*\*\*\*\*|对象ID

 |
|ObjectName|String|we\*\*\*\*\*-default-vpc|对象名称

 |
|ObjectType|String|vpc|对象类型

 |
|PrimaryUserId|String|1036052989950239|主要用户ID

 |
|PrimaryUserName|String|""|主用户名

 |
|SecondUserId|String|""|次用户ID

 |
|SecondUserName|String|""|次用户名

 |
|TraceId|String|wc-5d1dac8f08350d1dd94\*\*\*\*\*|事件跟踪ID

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PageNumber|Integer|1|查询页面数量

 |
|PageSize|Integer|10|查询页面大小

 |
|RequestId|String|F975CCFF-CA3D-41C2-8004-362D232\*\*\*\*\*|请求ID

 |
|TotalCount|Integer|1|查询结果总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/event?ServiceCode=webx&PageSize=1&PageNumber=10&EnvId=we-5d1dac8e08350d1dd94*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeEventsResponse>
    <PageNumber>10</PageNumber>
    <TotalCount>56</TotalCount>
    <Message>success</Message>
    <PageSize>1</PageSize>
    <RequestId>706D234F-37E4-4105-B226-92CA15D*****</RequestId>
    <Events>
        <Event>
            <AppId>wa-5d1af9c802470221ab7*****</AppId>
            <EventId>f0229b5a-79d2-4412-b039-f07fc96*****</EventId>
            <MsgCode>webx.wam.change.apply.success</MsgCode>
            <ObjectAttrs></ObjectAttrs>
            <EventLevel>INFO</EventLevel>
            <ObjectType>change</ObjectType>
            <EventMessage>Change wc-5d39b8bc6786bd4b149***** finish successfully, taking 108 seconds</EventMessage>
            <EnvId>we-5d39b8ba6786bd4b149*****</EnvId>
            <EventTimestamp>1564064041112</EventTimestamp>
            <PrimaryUserId>10360529899*****</PrimaryUserId>
            <MsgParams>
                <MsgParam>wc-5d39b8bc6786bd4b149*****</MsgParam>
                <MsgParam>108</MsgParam>
            </MsgParams>
            <TraceId>wc-5d39b8bc6786bd4b149*****</TraceId>
            <ObjectName></ObjectName>
            <ObjectId>wc-5d39b8bc6786bd4b149*****</ObjectId>
        </Event>
    </Events>
    <Code>OK</Code>
</DescribeEventsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":10,
	"TotalCount":56,
	"Message":"success",
	"PageSize":1,
	"RequestId":"232F3429-F58D-4A7A-9309-17C7F41*****",
	"Events":{
		"Event":[
			{
				"AppId":"wa-5d1af9c802470221ab7*****",
				"EventId":"f0229b5a-79d2-4412-b039-f07fc96*****",
				"MsgCode":"webx.wam.change.apply.success",
				"ObjectAttrs":{
					"ObjectAttr":[]
				},
				"EventLevel":"INFO",
				"ObjectType":"change",
				"EnvId":"we-5d39b8ba6786bd4b149*****",
				"EventMessage":"Change wc-5d39b8bc6786bd4b149***** finish successfully, taking 108 seconds",
				"EventTimestamp":1564064041112,
				"PrimaryUserId":"10360529899*****",
				"MsgParams":{
					"MsgParam":[
						"wc-5d39b8bc6786bd4b149*****",
						"108"
					]
				},
				"TraceId":"wc-5d39b8bc6786bd4b149*****",
				"ObjectName":"",
				"ObjectId":"wc-5d39b8bc6786bd4b149*****"
			}
		]
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

