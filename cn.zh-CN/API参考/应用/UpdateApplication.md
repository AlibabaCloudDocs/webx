# UpdateApplication {#doc_api_WebPlus_UpdateApplication .reference}

调用UpdateApplication更新应用。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=UpdateApplication&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
PUT /pop/v1/wam/application HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|是|wa-5d1af9c802470221ab7\*\*\*\*\*|应用ID，将更新此应用的信息

 |
|AppDescription|String|否|This is a updated Description|应用描述信息

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Application| | |返回的应用信息数据

 |
|AppDescription|String|This is a updated Description|应用描述

 |
|AppId|String|wa-5d1af9c802470221ab7\*\*\*\*\*|应用ID

 |
|AppName|String|user1|应用名称

 |
|CategoryName|String|Java|应用类型

 |
|CreateTime|Long|1562048968834|应用创建时间

 |
|CreateUsername|String|user1|应用创建者

 |
|UpdateTime|Long|1564139945132|应用最后更新时间

 |
|UpdateUsername|String|user1|应用最后更新者

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|18A1F87E-591D-4491-90D5-2B101FA\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/application&<公共请求参数>
{
  "AppId":"wa-5d1af9c802470221ab7*****",
  "AppDescription":"This is a updated Description"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateApplicationResponse>
    <Message>success</Message>
    <RequestId>FBE82ECD-4200-4390-BEAC-B1CCF14*****</RequestId>
    <Application>
        <CategoryName>Java</CategoryName>
        <UpdateUsername>user1</UpdateUsername>
        <CreateUsername>user1</CreateUsername>
        <CreateTime>1562048968834</CreateTime>
        <AppId>wa-5d1af9c802470221ab7*****</AppId>
        <AppDescription>This is a updated Description</AppDescription>
        <UpdateTime>1564139945498</UpdateTime>
        <AppName>user1</AppName>
    </Application>
    <Code>OK</Code>
</UpdateApplicationResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"Application":{
		"CategoryName":"Java",
		"UpdateUsername":"user1",
		"CreateUsername":"user1",
		"CreateTime":1562048968834,
		"AppId":"wa-5d1af9c802470221ab7*****",
		"UpdateTime":1564139945132,
		"AppDescription":"This is a updated Description",
		"AppName":"user1"
	},
	"RequestId":"DBF81777-FD55-4A42-818F-FBC2F3E*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

