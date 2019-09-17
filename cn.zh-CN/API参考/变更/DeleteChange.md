# DeleteChange {#doc_api_WebPlus_DeleteChange .reference}

调用DeleteChange删除一个变更。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DeleteChange&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
DELETE /pop/v1/wam/change HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChangeId|String|是|wc-5d3a963d5802611c4dd\*\*\*\*\*|变更ID，将删除此变更

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|671FBCF3-D384-4DC4-B6F4-028C28E\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/change?ServiceCode=webx&Id=wc-5d245f94f314934e2ab1*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteChangeResponse>
    <Message>success</Message>
    <RequestId>671FBCF3-D384-4DC4-B6F4-028C28*****</RequestId>
    <Code>OK</Code>
</DeleteChangeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"671FBCF3-D384-4DC4-B6F4-028C28E*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|OSSDisabled|You have not activated the OSS service and cannot use the WebPlus service. Please go to the OSS console \(https://oss.console.aliyun.com\) to activate OSS and try again.|您没有开通 OSS 服务，不能使用 WebPlus 服务，请前往 OSS 控制台\(https://oss.console.aliyun.com\) 开通后重试。|
|400|OSSApiCallFailed|When initializing applications, updating configurations, or destroying applications, WebPlus attempts to communicate with OSS through API communication. An OSS service throw error occurred. The bucket or the file does not exist.|在初始化应用、更新配置、以及销毁应用时，WebPlus 尝试与 OSS 进行 API 通信出现 OSS 服务抛出的异常，如 bucket 不存在、文件不存在等。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

