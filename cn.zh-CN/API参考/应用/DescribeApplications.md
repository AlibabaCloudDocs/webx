# DescribeApplications {#doc_api_WebPlus_DescribeApplications .reference}

调用DescribeApplications查询应用信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeApplications&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/application HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|否|wa-5d1af9c802470221ab7\*\*\*\*\*|应用ID，查询特定应用信息

 |
|AppName|String|否|appTest|应用名称，查询此名称的应用

 |
|AppSearch|String|否|appSearch|查询的应用名关键字，若应用名称包含此关键字，则返回此应用的关键字

 |
|EnvSearch|String|否|testEnv|搜索应用中环境名的关键字，若应用中的环境名包含此关键字，则返回此应用

 |
|PageNumber|Integer|否|1|查询页面数

 |
|PageSize|Integer|否|10|查询页面大小

 |
|StackSearch|String|否|Java|栈类型搜索

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Applications| | |应用列表

 |
|AppDescription|String|This is an application.|应用描述

 |
|AppId|String|wa-5d1af9c802470221ab7\*\*\*\*\*|应用ID

 |
|AppName|String|appName|应用名称

 |
|CategoryName|String|Java|应用类型

 |
|CreateTime|Long|1562226969419|应用创建时间

 |
|CreateUsername|String|webx-test|应用创建者

 |
|RunningEnvs|Integer|2|运行中的环境数量

 |
|TerminatedEnvs|Integer|0|已终止的环境数量

 |
|TotalEnvs|Integer|2|应用中总环境数量

 |
|UpdateTime|Long|1562226969419|应用上次更新时间

 |
|UpdateUsername|String|webx-test|应用上次更新者

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PageNumber|Integer|1|查询页面数量

 |
|PageSize|Integer|20|查询页面大小

 |
|RequestId|String|132BF104-A660-40C7-936B-F805967\*\*\*\*\*|请求ID

 |
|TotalCount|Integer|1|查询结果总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/application?PageSize=20&EnvSearch=test?<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeApplicationsResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <Message>success</Message>
    <PageSize>20</PageSize>
    <RequestId>761C51B0-9026-4659-989C-7AFDFEE*****</RequestId>
    <Applications>
        <Application>
            <CategoryName>Java</CategoryName>
            <UpdateUsername>user1</UpdateUsername>
            <CreateUsername>user1</CreateUsername>
            <CreateTime>1562048968834</CreateTime>
            <AppId>wa-5d1af9c802470221ab7*****</AppId>
            <TotalEnvs>2</TotalEnvs>
            <UpdateTime>1562048968834</UpdateTime>
            <AppDescription></AppDescription>
            <AppName>test</AppName>
            <TerminatedEnvs>0</TerminatedEnvs>
            <RunningEnvs>2</RunningEnvs>
        </Application>
    </Applications>
    <Code>OK</Code>
</DescribeApplicationsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"Message":"success",
	"PageSize":20,
	"RequestId":"00C3CEDB-9E1B-4872-985E-BB2B7D6*****",
	"Applications":{
		"Application":[
			{
				"CategoryName":"Java",
				"UpdateUsername":"user1",
				"CreateUsername":"user1",
				"CreateTime":1562048968834,
				"AppId":"wa-5d1af9c802470221ab7*****",
				"UpdateTime":1562048968834,
				"TotalEnvs":2,
				"AppDescription":"",
				"AppName":"test",
				"TerminatedEnvs":0,
				"RunningEnvs":2
			}
		]
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

