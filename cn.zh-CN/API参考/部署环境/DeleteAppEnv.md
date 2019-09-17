# DeleteAppEnv {#doc_api_WebPlus_DeleteAppEnv .reference}

调用DeleteAppEnv删除一个环境。

**说明：** 环境在被删除前必须处于“已释放”状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DeleteAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
DELETE /pop/v1/wam/appEnv HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d39b8ba6786bd4b149\*\*\*\*\*|要删除的环境ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|348C6C36-F98C-46A2-B14C-B280D84\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv?Id=we-5d22bc1a6f48e5478fd*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteAppEnvResponse>
      <Message>success</Message>
      <RequestId>348C6C36-F98C-46A2-B14C-B280D84*****</RequestId>
      <Code>OK</Code>
</DeleteAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DeleteAppEnvResponse":{
		"Message":[
			"success"
		],
		"RequestId":[
			"348C6C36-F98C-46A2-B14C-B280D84*****"
		],
		"Code":[
			"OK"
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|404|DeletingEnvNotExists|Deleting environment failed. The specified environment does not exist.|删除应用环境失败，将被删除的环境不存在。|
|403|DeleteEnvNotAllowed|You cannot delete an environment when the environment is abandoning an update, performing a change, or when the status is not “terminated".|删除应用环境失败，当环境处正在：放弃某次更新、正在执行变更、同时状态不是 "终止"时；不允许删除环境的操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

