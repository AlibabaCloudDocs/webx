# CreateApplication {#doc_api_WebPlus_CreateApplication .reference}

使用CreateApplication创建一个新应用。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=CreateApplication&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/application HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppDescription|String|否|This is an application|应用描述信息

 |
|AppName|String|否|app1|新建应用的名称

 |
|CategoryName|String|否|Java|新建应用的平台类型

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Application| | |应用信息

 |
|AppDescription|String|This is an application|应用描述信息

 |
|AppId|String|wa-5d3ea7cf2977ca5251e\*\*\*\*\*|应用ID

 |
|AppName|String|newApplication|应用名称

 |
|CategoryName|String|Java|应用类型

 |
|CreateTime|Long|1562333864469|应用创建时间

 |
|CreateUsername|String|userName|应用创建者

 |
|UpdateTime|Long|1562333864469|应用上次更新时间

 |
|UpdateUsername|String|userName|应用上次更新者

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|BFD4C1BA-897D-4306-A79D-4D20D7E\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/application?ServiceCode=webx&<公共请求参数>
{
  "AppName","app1",
  "AppDescription","This is an application",
  "CategoryName","Java",
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateApplicationResponse>
      <Message>success</Message>
      <Application>
            <AppName>newApplication</AppName>
            <CategoryName>Java</CategoryName>
            <AppDescription>This is an application.</AppDescription>
            <UpdateUsername>yourUsername</UpdateUsername>
            <CreateUsername>yourUsername</CreateUsername>
            <CreateTime>1562333864469</CreateTime>
            <UpdateTime>1562333864469</UpdateTime>
            <AppId>wa-5d243437f314934e2ab*****</AppId>
      </Application>
      <RequestId>BFD4C1BA-897D-4306-A79D-4D20D7E*****</RequestId>
      <Code>OK</Code>
</CreateApplicationResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"Application":{
		"CategoryName":"Java",
		"UpdateUsername":"yourUsername",
		"CreateUsername":"yourUsername",
		"CreateTime":1564387279787,
		"AppId":"wa-5d3ea7cf2977ca5251e*****",
		"UpdateTime":1564387279787,
		"AppDescription":"app desc",
		"AppName":"newApplication"
	},
	"RequestId":"27BE2428-060D-47DB-8A3C-CD86A53*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|CategoryNotExists|The specified application category does not exist.|根据所使用的应用类型名称没有找到对应的记录，可能是配置错误或参数错误。|
|400|AppNameUsed|The specified application name already exists in this region. Enter another application name.|创建应用时所使用的应用名称已被占用，应用名在不同的 Region 下可重名；请更换名字后重试此操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

