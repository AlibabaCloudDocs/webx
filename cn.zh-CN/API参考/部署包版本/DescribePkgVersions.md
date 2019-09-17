# DescribePkgVersions {#doc_api_WebPlus_DescribePkgVersions .reference}

调用DescribePkgVersions查询部署包版本。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribePkgVersions&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/pkgVersion HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|是|wa-5d1d9d8c85c7f86\*\*\*\*\*\*\*\*\*\*|应用ID，表示部署包版本所在的应用

 |
|PageNumber|Integer|否|1|查询页面大小

 |
|PageSize|Integer|否|10|查询页面数

 |
|PkgVersionLabel|String|否|version-demo-tmc-1.4|部署包版本标签

 |
|PkgVersionSearch|String|否|tmc|部署包版本标签搜索关键字，将返回含有此关键字的部署包版本

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PageNumber|Integer|1|查询页面数量

 |
|PageSize|Integer|10|查询页面大小

 |
|PkgVersions| | |查询版本结果

 |
|AppId|String|wa-5d1d9d8c85c7f86e2ef\*\*\*\*\*|应用ID，表示部署包版本所在的应用

 |
|AppName|String|App1|应用ID，表示部署包版本所在的应用

 |
|CreateTime|Long|1562246822377|部署包版本的更新时间

 |
|CreateUsername|String|baiji|部署包版本建立者

 |
|PackageSource|String|resources/userName/versions/version-demo-tmc-1.4/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war|部署包版本的资源包

 |
|PkgVersionDescription|String|This is a package.|部署包版本描述

 |
|PkgVersionId|String|wp-5d244f33f314934e2ab\*\*\*\*\*|部署包版本ID

 |
|PkgVersionLabel|String|version-demo-tmc-1.5|部署包版本标签

 |
|UpdateTime|Long|1562246822377|部署包版本的更新时间

 |
|RequestId|String|9ADFCBC1-3315-4E97-B5A3-406528B\*\*\*\*\*|请求ID

 |
|TotalCount|Integer|1|查询结果总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://webplus.cn-hangzhou.aliyuncs.com/?AppId=wa-5d1d9d8c85c7f*****fb7234
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribePkgVersionsResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <Message>success</Message>
    <PageSize>10</PageSize>
    <RequestId>D2F23007-1F7F-4532-852E-6127B18*****</RequestId>
    <PkgVersions>
        <PkgVersion>
            <PackageSource>resources/user1/versions/version-demo-tmc-1.5/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war</PackageSource>
            <PkgVersionDescription>This is a package.</PkgVersionDescription>
            <CreateUsername>user1</CreateUsername>
            <CreateTime>1562660659387</CreateTime>
            <AppId>wa-5d1d9d8c85c7f86e2ef*****</AppId>
            <UpdateTime>1562660659387</UpdateTime>
            <PkgVersionLabel>version-demo-tmc-1.5</PkgVersionLabel>
            <PkgVersionId>wp-5d244f33f314934e2ab*****</PkgVersionId>
        </PkgVersion>
    </PkgVersions>
    <Code>OK</Code>
</DescribePkgVersionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"Message":"success",
	"PageSize":10,
	"RequestId":"39A380A0-5A5F-4832-B27D-AAB8318*****",
	"PkgVersions":{
		"PkgVersion":[
			{
				"PackageSource":"resources/userName/versions/version-demo-tmc-1.5/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war",
				"PkgVersionDescription":"This is a package.",
				"CreateUsername":"user1",
				"CreateTime":1562660659387,
				"AppId":"wa-5d1d9d8c85c7f86e2ef*****",
				"UpdateTime":1562660659387,
				"Label":"version-demo-tmc-1.5",
				"PkgVersionId":"wp-5d244f33f314934e2ab*****"
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

