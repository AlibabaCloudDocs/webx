# DescribeStacks {#doc_api_WebPlus_DescribeStacks .reference}

调用DescribeStacks查询技术栈。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeStacks&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/stack HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CategoryName|String|否|Java|技术栈类型名称

 |
|PageNumber|Integer|否|1|查询页面数

 |
|PageSize|Integer|否|10|查询页面大小

 |
|RecommendedOnly|Boolean|否|true|仅查询推荐的技术栈

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|查询页面数量

 |
|Message|String|success|响应消息，若成功请求为success

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|PageSize|Integer|10|查询页面大小

 |
|RequestId|String|E95B3D91-ED61-4715-AAD1-7E496A\*\*\*\*\*6|请求ID

 |
|Stacks| | |技术栈查询结果列表

 |
|CreateTime|Long|1553218065000|技术栈创建时间

 |
|UpdateTime|Long|1553218065000|最后更新时间

 |
|VersionCode|Integer|10|最后更新者

 |
|TotalCount|Integer|1|查询结果总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/stack?ServiceCode=webx&Category=Java&PageSize=10&PageNumber=1&RecommendedOnly=true&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeStacksResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <Message>success</Message>
    <PageSize>10</PageSize>
    <RequestId>2581EA69-00C2-44F8-85DD-1F1*****44D7</RequestId>
    <Stacks>
        <Stack>
            <LatestStack>true</LatestStack>
            <CategoryName>Java</CategoryName>
            <RecommendedStack>true</RecommendedStack>
            <StackId>ws-6c937c98a9c*****0c4823984</StackId>
            <CreateTime>1553218065000</CreateTime>
            <VersionCode>10</VersionCode>
            <UpdateTime>1553218065000</UpdateTime>
            <StackName>Java 8 / Aliyun Linux 2.1903</StackName>
        </Stack>
    </Stacks>
    <Code>OK</Code>
</DescribeStacksResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"Message":"success",
	"PageSize":10,
	"RequestId":"1EC2BF9F-20BA-4877-B9DC-89CA*****589",
	"Stacks":{
		"Stack":[
			{
				"LatestStack":true,
				"CategoryName":"Java",
				"RecommendedStack":true,
				"StackId":"ws-6c937c98a9*****d0c4823984",
				"CreateTime":1553218065000,
				"VersionCode":10,
				"UpdateTime":1553218065000,
				"StackName":"Java 8 / Aliyun Linux 2.1903"
			}
		]
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

