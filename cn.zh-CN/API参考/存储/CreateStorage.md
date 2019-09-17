# CreateStorage {#doc_api_WebPlus_CreateStorage .reference}

调用CreateStorage创建一个存储桶。

需要先开通OSS服务才能创建存储，具体见 https://oss.console.aliyun.com

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=CreateStorage&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/storage HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|E61A371C-53D9-4F66-A90E-4FC09EE\*\*\*\*\*|请求ID

 |
|Storage| | |存储桶信息

 |
|BucketName|String|webplus-cn-shenzhen-s-5d01fab421ed1528121\*\*\*\*\*|存储桶的bucket名

 |
|CreateTime|Long|1564388637126|存储桶创建时间

 |
|UpdateTime|Long|1564388637126|上次更新时间

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/storage?ServiceCode=webx&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateStorageResponse>
    <Storage>
        <BucketName>webplus-cn-shenzhen-s-5d01fab421ed1528121*****</BucketName>
        <CreateTime>1564388637551</CreateTime>
        <UpdateTime>1564388637551</UpdateTime>
    </Storage>
    <Message>success</Message>
    <RequestId>3373E77A-9FDF-4B7F-981F-17C2446*****</RequestId>
    <Code>OK</Code>
</CreateStorageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Storage":{
		"BucketName":"webplus-cn-shenzhen-s-5d01fab421ed1528121*****",
		"CreateTime":1564388637126,
		"UpdateTime":1564388637126
	},
	"Message":"success",
	"RequestId":"E229C81C-2315-46B0-A5D7-3C2BA73*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|OSSDisabled|You have not activated the OSS service and cannot use the WebPlus service. Please go to the OSS console \(https://oss.console.aliyun.com\) to activate OSS and try again.|您没有开通 OSS 服务，不能使用 WebPlus 服务，请前往 OSS 控制台\(https://oss.console.aliyun.com\) 开通后重试。|
|400|OSSApiCallFailed|When initializing applications, updating configurations, or destroying applications, WebPlus attempts to communicate with OSS through API communication. An OSS service throw error occurred. The bucket or the file does not exist.|在初始化应用、更新配置、以及销毁应用时，WebPlus 尝试与 OSS 进行 API 通信出现 OSS 服务抛出的异常，如 bucket 不存在、文件不存在等。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

