# CreatePkgVersion {#doc_api_WebPlus_CreatePkgVersion .reference}

调用CreatePkgVersion创建一个部署包版本。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=CreatePkgVersion&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/pkgVersion HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|否|wa-5d3eaae92977ca5251e\*\*\*\*\*|建立部署包版本的应用ID

 |
|PackageSource|String|否|oss://target-url/webx/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war|用于建立部署包版本的资源包

 |
|PkgVersionDescription|String|否|This is a package.|版本描述信息

 |
|PkgVersionLabel|String|否|version-demo-tmc-1.5|版本标签

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|PkgVersion| | |部署包版本信息

 |
|AppId|String|wa-5d3eaae92977ca5251e\*\*\*\*\*|应用ID

 |
|AppName|String|app1|应用名称

 |
|CreateTime|Long|1564388159130|部署包创建时间

 |
|PackageSource|String|oss://target-url/webx/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war|部署包资源位置，用于建立部署包版本的资源

 |
|PkgVersionDescription|String|This is a package|部署包版本描述

 |
|PkgVersionId|String|wp-5d3eab3f2977ca5251e\*\*\*\*\*|部署包版本ID

 |
|PkgVersionLabel|String|version-demo-tmc-1.5|部署包版本标签

 |
|UpdateTime|Long|1564388159130|上次更新时间

 |
|RequestId|String|14A65FB3-DFD6-4D9A-83EA-9259C2D\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/pkgVersion?ServiceCode=webx&<公共请求参数>
{
   "PkgVersionLabel","version-demo-tmc-1.5",
   "PkgVersionDescription","This is a package.",
   "AppId","wa-5d3eaae92977ca5251e*****",
   "PackageSource","oss://target-url/webx/webx-quickstart-tomcat-0.1.0-SNAPSHOT.war"

}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreatePkgVersionResponse>
      <Message>success</Message>
      <RequestId>257C2FA9-3316-4BCB-9DB7-219A7A0*****</RequestId>
      <PkgVersion>
            <PkgVersionDescription>This is a package.</PkgVersionDescription>
            <CreateTime>1562246822377</CreateTime>
            <AppId>wa-5d1d9d8c85c7f86e2ef*****</AppId>
            <UpdateTime>1562246822377</UpdateTime>
            <PkgVersionLabel>version-demo-tmc-1.4</PkgVersionLabel>
            <PkgVersionId>wp-5d244f33f314934e2ab*****</PkgVersionId>
      </PkgVersion>
      <Code>OK</Code>
</CreatePkgVersionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PkgVersion":{
		"PkgVersionDescription":"This is a package.",
		"CreateTime":1564388159130,
		"PkgVersionLabel":"version-demo-tmc-1.5",
		"AppId":"wa-5d3eaae92977ca5251e*****",
		"UpdateTime":1564388159130,
		"PkgVersionId":"wp-5d3eab3f2977ca5251e*****"
	},
	"Message":"success",
	"RequestId":"257C2FA9-3316-4BCB-9DB7-219A7A0*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|VersionLabelExists|An error occurred while creating an application version. The version name already exists. Please use a different name and try again.|创建应用版本失败，版本名称已经存在，请更换版本名称后重试此次操作。|
|400|OSSPathInvalid|The specified OSS path is invalid. For more information about OSS path, see oss://webx-demo/directory/file.json|非法的 OSS 路径，OSS 路径请参考: oss://webx-demo/directory/file.json|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

