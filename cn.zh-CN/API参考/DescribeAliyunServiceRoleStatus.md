# DescribeAliyunServiceRoleStatus {#doc_api_WebPlus_DescribeAliyunServiceRoleStatus .reference}

调用DescribeAliyunServiceRoleStatus查询阿里云服务角色状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeAliyunServiceRoleStatus&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/paas/aliyunServiceRoleStatus HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|491B2CBE-D042-432B-BD44-C02564C\*\*\*\*\*|请求ID

 |
|Roles| | |角色列表

 |
|RoleDesc|String|To improve product security, Web+ needs to be authorized by the user's primary account to access your resources such as ECS, OSS, and SLB.|角色描述

 |
|RoleExists|Boolean|true|角色是否存在

 |
|RoleName|String|AliyunWebPlusDefaultRole|角色名称

 |
|RoleTemplateId|String|DefaultRole|角色模板ID

 |
|ServiceName|String|WebPlus|服务名称

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/paas/aliyunServiceRoleStatus&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAliyunServiceRoleStatusResponse>
    <Message>success</Message>
    <RequestId>491B2CBE-D042-432B-BD44-C02564C*****</RequestId>
    <Code>OK</Code>
    <Roles>
        <Role>
            <RoleName>AliyunWebPlusDefaultRole</RoleName>
            <RoleExists>true</RoleExists>
            <ServiceName>WebPlus</ServiceName>
            <RoleDesc>To improve product security, Web+ needs to be authorized by the user's primary account to access your resources such as ECS, OSS, and SLB.</RoleDesc>
            <RoleTemplateId>DefaultRole</RoleTemplateId>
        </Role>
        <Role>
            <RoleName>AliyunECSInstanceForWebPlusRole</RoleName>
            <RoleExists>true</RoleExists>
            <ServiceName>ECS</ServiceName>
            <RoleDesc>To improve product security, ECS instances need to be authorized by the user's primary account to access your Web+ and OSS resources.</RoleDesc>
            <RoleTemplateId>ForWebPlus</RoleTemplateId>
        </Role>
    </Roles>
</DescribeAliyunServiceRoleStatusResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"7BFDE59D-619B-4E8D-9D4C-B5CDAA0*****",
	"Code":"OK",
	"Roles":{
		"Role":[
			{
				"RoleName":"AliyunWebPlusDefaultRole",
				"RoleExists":true,
				"ServiceName":"WebPlus",
				"RoleDesc":"To improve product security, Web+ needs to be authorized by the user's primary account to access your resources such as ECS, OSS, and SLB.",
				"RoleTemplateId":"DefaultRole"
			},
			{
				"RoleName":"AliyunECSInstanceForWebPlusRole",
				"RoleExists":true,
				"ServiceName":"ECS",
				"RoleDesc":"To improve product security, ECS instances need to be authorized by the user's primary account to access your Web+ and OSS resources.",
				"RoleTemplateId":"ForWebPlus"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

