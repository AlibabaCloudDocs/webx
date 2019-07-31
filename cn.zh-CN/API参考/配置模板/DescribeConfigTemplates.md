# DescribeConfigTemplates {#doc_api_WebPlus_DescribeConfigTemplates .reference}

调用DescribeConfigTemplates查询配置模板。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeConfigTemplates&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/configTemplate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|是|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID，查询此应用上的配置模板

 |
|PageNumber|Integer|否|1|查询页面数量

 |
|PageSize|Integer|否|10|查询页面大小

 |
|TemplateName|String|否|template-name|要查询的配置模板名称

 |
|TemplateSearch|String|否|template|查询的模版名称关键字

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|ConfigTemplates| | |配置结果项数组

 |
|AppId|String|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID，要查询此应用上的模板

 |
|AppName|String|testApplication|应用名称，表示配置模板所在的应用

 |
|CreateTime|Long|1562298470970|配置模板的建立时间

 |
|PkgVersionId|String|wp-5d1daece08350d1dd94\*\*\*\*\*|部署包版本ID

 |
|PkgVersionLabel|String|1562226365|部署包版本标签

 |
|StackId|String|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈ID

 |
|StackName|String|Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903|技术栈名称

 |
|TemplateDescription|String|this is a new description.|配置模板的描述信息

 |
|TemplateId|String|wct-5d1eca8dd56beb722b7\*\*\*\*\*|配置模板ID

 |
|TemplateName|String|new-template-name|配置模板名称

 |
|UpdateTime|Long|1562298470970|配置模板更新时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PageNumber|Integer|1|查询页面数量

 |
|PageSize|Integer|10|查询页面大小

 |
|RequestId|String|5CD6AF45-920A-4F5C-BD00-B41D6AE\*\*\*\*\*|请求ID

 |
|TotalCount|Integer|1|结果总数量

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/configTemplate?ServiceCode=webx&AppId=wa-5d1d9d8c85c7f86e2ef*****&PageSize=10&PageNumber=1&Search=template&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeConfigTemplatesResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <Message>success</Message>
    <PageSize>10</PageSize>
    <RequestId>9CFC8370-B02A-40EE-AAB8-8005DA9*****</RequestId>
    <ConfigTemplates>
        <ConfigTemplate>
            <TemplateName>new-template-name</TemplateName>
            <TemplateDescription>this is a new description.</TemplateDescription>
            <StackId>ws-6c937c98a9c0296d0c48*****</StackId>
            <CreateTime>1562299021581</CreateTime>
            <PkgVersionLabel>1562226365</PkgVersionLabel>
            <AppId>wa-5d1d9d8c85c7f86e2ef*****</AppId>
            <UpdateTime>1562577497233</UpdateTime>
            <AppName>user1</AppName>
            <TemplateId>wct-5d1eca8dd56beb722b7*****</TemplateId>
            <PkgVersionId>wp-5d1daece08350d1dd94*****</PkgVersionId>
            <StackName>Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903</StackName>
        </ConfigTemplate>
    </ConfigTemplates>
    <Code>OK</Code>
</DescribeConfigTemplatesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"Message":"success",
	"PageSize":10,
	"RequestId":"4D769F04-E1C2-49A6-8A5B-017E2EF*****",
	"ConfigTemplates":{
		"ConfigTemplate":[
			{
				"TemplateName":"new-template-name",
				"TemplateDescription":"this is a new description.",
				"StackId":"ws-6c937c98a9c0296d0c48*****",
				"CreateTime":1562299021581,
				"PkgVersionLabel":"1562226365",
				"AppId":"wa-5d1d9d8c85c7f86e2ef*****",
				"UpdateTime":1562577497233,
				"AppName":"user1",
				"PkgVersionId":"wp-5d1daece08350d1dd94*****",
				"StackName":"Tomcat 8.5 / Java 8 / Aliyun Linux 2.1903",
				"TemplateId":"wct-5d1eca8dd56beb722b7*****"
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
|400|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

