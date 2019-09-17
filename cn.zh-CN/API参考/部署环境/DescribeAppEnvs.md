# DescribeAppEnvs {#doc_api_WebPlus_DescribeAppEnvs .reference}

调用DescribeAppEnvs查询符合条件的部署环境。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeAppEnvs&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/appEnv HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|是|wa-5cef9f96dd351b61df0\*\*\*\*\*|环境所属的应用ID

 |
|EnvId|String|否|we-5d22b3816f48e5478fd\*\*\*\*\*|环境ID

 |
|EnvName|String|否|Test1|环境名称

 |
|EnvSearch|String|否|Test|环境搜索关键字

 |
|IncludeTerminated|Boolean|否|true|是否包含已释放的环境

 |
|PageNumber|Integer|否|1|查询页数，默认为第1页

 |
|PageSize|Integer|否|10|每页查询数据量，默认为10条

 |
|RecentUpdated|Boolean|否|false|是否查询最近变更环境，默认为false

 |
|StackSearch|String|否|Java|技术栈搜索关键字

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AppEnvs| | |环境列表

 |
|AbortingChange|Boolean|false|环境是否正在取消变更

 |
|AppId|String|wa-5cef9f96dd351b61df0\*\*\*\*\*|环境所属的应用ID

 |
|AppName|String|test|应用名称

 |
|ApplyingChange|Boolean|false|环境是否正在变更

 |
|CategoryName|String|Java|环境技术栈类型

 |
|ChangeBanner|String|Web+正在变更您的环境|变更提示

 |
|CreateTime|Long|1560246554242|环境创建时间

 |
|CreateUsername|String|test|创建环境的用户名

 |
|DataRoot|String|wproot|数据文件存储根目录

 |
|EnvDescription|String|This is an env.|环境描述信息

 |
|EnvId|String|we-5d22b3816f48e5478fd\*\*\*\*\*|环境ID

 |
|EnvName|String|test|环境名称

 |
|EnvStatus|String|RUNNING|环境运行状态

 |
|EnvType|String|web|环境类型

 |
|LastEnvStatus|String|RUNNING|环境上次变更前状态

 |
|LatestChangeId|String|wc-5d22c046b767ab0fc64\*\*\*\*\*|环境上次变更ID

 |
|LogBase|String|logs/yourJava-java/environments/Test2/|日志存储根目录

 |
|PkgVersionId|String|wp-5d1c0a5d913567334af\*\*\*\*\*|部署版本包ID

 |
|PkgVersionLabel|String|20190703.095155|部署版本名称

 |
|PkgVersionStorageKey|String|webplus-demo-java-0.1.0-SNAPSHOT-exec.jar|部署包版本文件

 |
|StackId|String|ws-6c937c98a9c0296d0c48\*\*\*\*\*|技术栈ID

 |
|StackName|String|Java 8 / Aliyun Linux 2.1903|技术栈名称

 |
|StorageBase|String|resources/yourJava-java/environments/Test2/|环境存储根目录

 |
|TotalInstances|Long|1|环境总实例数

 |
|UpdateTime|Long|1562557466136|更新时间

 |
|UpdateUsername|String|test|更新用户名

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PageNumber|Integer|10|每页查询数据量

 |
|PageSize|Integer|1|查询页数

 |
|RequestId|String|D435EBFB-623E-47FB-A55A-C0F4C8B\*\*\*\*\*|请求ID

 |
|TotalCount|Integer|1|总记录条数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv?&AppId=wa-5cef9f96dd351b61df0*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAppEnvsResponse>
    <AppEnvs>
        <AppEnv>
            <LatestChangeId>wc-5d135e524f2c7336e33*****</LatestChangeId>
            <Type>web</Type>
            <DataRoot>wproot</DataRoot>
            <ApplyingChange>false</ApplyingChange>
            <AppId>wa-5cef9f96dd351b61df0*****</AppId>
            <StackName>Java 8 / Aliyun Linux 2.1903</StackName>
            <PkgVersionStorageKey>webplus-demo-java-0.1.0-SNAPSHOT-exec.jar</PkgVersionStorageKey>
            <CreateUsername>test</CreateUsername>
            <AppName>sanwei-java</AppName>
            <LastEnvStatus>TERMINATING</LastEnvStatus>
            <PkgVersionId>wp-5cff7917c6af395bed9*****</PkgVersionId>
            <EnvDescription></EnvDescription>
            <LogBase>logs/test/environments/test/</LogBase>
            <StackId>ws-6c937c98a9c0296d0c48*****</StackId>
            <UpdateTime>1561550418955</UpdateTime>
            <TotalInstances>1</TotalInstances>
            <AbortingChange>false</AbortingChange>
            <EnvName>tefdsa</EnvName>
            <EnvStatus>TERMINATED</EnvStatus>
            <CategoryName>Java</CategoryName>
            <UpdateUsername>test</UpdateUsername>
            <StorageBase>resources/test/environments/test/</StorageBase>
            <CreateTime>1560246554242</CreateTime>
            <PkgVersionLabel>20190611.174849</PkgVersionLabel>
            <EnvId>we-5cff791ac6af395bed9*****</EnvId>
        </AppEnv>
    </AppEnvs>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <Message>success</Message>
    <PageSize>10</PageSize>
    <RequestId>46F9B039-C782-4E68-8881-7F63A63*****</RequestId>
    <Code>OK</Code>
</DescribeAppEnvsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AppEnvs":{
		"AppEnv":[
			{
				"LatestChangeId":"wc-5d135e524f2c7336e33*****",
				"DataRoot":"wproot",
				"Type":"web",
				"AppId":"wa-5cef9f96dd351b61df0*****",
				"StackName":"Java 8 / Aliyun Linux 2.1903",
				"EnvStatus":"TERMINATED",
				"PkgVersionStorageKey":"webplus-demo-java-0.1.0-SNAPSHOT-exec.jar",
				"EnvName":"test",
				"EnvId":"we-5cff791ac6af395bed9*****",
				"CreateUsername":"test",
				"AppName":"test",
				"PkgVersionId":"wp-5cff7917c6af395bed9*****",
				"AbortingChange":false,
				"CategoryName":"Java",
				"LogBase":"logs/test/environments/test/",
				"StackId":"ws-6c937c98a9c0296d0c48*****",
				"UpdateTime":1561550418955,
				"TotalInstances":1,
				"EnvDescription":"",
				"LastEnvStatus":"TERMINATING",
				"UpdateUsername":"test",
				"StorageBase":"resources/yourJava-java/environments/tefdsa/",
				"ApplyingChange":false,
				"CreateTime":1560246554242,
				"PkgVersionLabel":"20190611.174849"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":1,
	"Message":"success",
	"PageSize":10,
	"RequestId":"D435EBFB-623E-47FB-A55A-C0F4C8B*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|AppNotExist|A corresponding application was not found based on the application ID.|根据应用 ID 没有找到对应的应用。|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

