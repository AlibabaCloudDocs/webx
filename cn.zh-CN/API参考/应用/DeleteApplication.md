# DeleteApplication {#doc_api_WebPlus_DeleteApplication .reference}

调用DeleteApplication删除一个应用。

**说明：** 删除应用前需保证应用内所部署的**所有环境**均已处于**已终止**状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DeleteApplication&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
DELETE /pop/v1/wam/application HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AppId|String|是|wa-5d1af9c802470221ab7\*\*\*\*\*|应用ID，将删除此应用

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功，则返回OK

 |
|Message|String|success|响应消息，若成功，则返回success

 |
|RequestId|String|ED18C0F9-D542-4EE0-A3EE-BD71A6A\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/application?ServiceCode=webx&Id=wa-5d243437f314934e2a*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteApplicationResponse>
      <Message>success</Message>
      <RequestId>ED18C0F9-D542-4EE0-A3EE-BD71A6A*****</RequestId>
      <Code>OK</Code>
</DeleteApplicationResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"ED18C0F9-D542-4EE0-A3EE-BD71A6A*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|403|AppDeleteNotAllowed|You cannot delete this application. Make sure that all deployment environments in this application are terminated.|不允许删除该应用，如果该应用下有部署环境，需要确保所有环境均处于 终止 状态才能删除应用，请检查对应环境的状态后重试。|
|404|DeletingEnvNotExists|Deleting environment failed. The specified environment does not exist.|删除应用环境失败，将被删除的环境不存在。|
|400|EnvDeleteFailed|An error occurred while deleting the application environment. This environment may have been deleted, or an error occurred while the server was deleting the environment configuration.|删除应用环境失败，有可能此环境之前已经被删除；或服务器删除环境配置时发生错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

