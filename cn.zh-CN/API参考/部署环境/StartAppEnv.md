# StartAppEnv {#doc_api_WebPlus_StartAppEnv .reference}

调用StartAppEnv启动一个部署环境。

-   只能针对状态处于**已停止**的环境执行停止操作。
-   此API被调用后将返回此次创建的变更ID，可以使用此ID查询变更信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=StartAppEnv&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/appEnv/start HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID，将启动此环境

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChange| | |环境变更响应信息

 |
|ChangeId|String|wc-5d247bbcd43be51c729\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|StartTime|String|1562672060867|变更开始时间

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|8D69F3C4-EA43-49D5-875A-0893BF\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/appEnv/start??Id=we-5d22b3816f48e5478fd*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<StarAppEnvResponse>
    <EnvChange>
        <ChangeId>wc-5d247ab5d43be51c729*****</ChangeId>
        <EnvId>we-5d247866d43be51c729*****</EnvId>
        <StartTime>1562671797841</StartTime>
    </EnvChange>
    <Message>success</Message>
    <RequestId>05BB8B43-DAA6-4E19-9A3C-AF11DD1*****</RequestId>
    <Code>OK</Code>
</StarAppEnvResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"633D9443-025A-4B39-8957-495CC2B*****",
	"EnvChange":{
		"EnvId":"we-5d247866d43be51c729*****",
		"ChangeId":"wc-5d247bbcd43be51c729*****",
		"StartTime":1562672060867
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|403|StatusNotAllowedStart|A start action can only be made to an environment that is already stopped. An environment with other status cannot be started.|应用启动只能针对已经停止的应用环境状态进行，其他状态不允许启动。|
|400|EnvOnChanging|An error occurred while starting the change. Wait until the ongoing change is complete.|变更启动失败，原因是上一个变更正在进行，请等待上一次变更完成后再继续。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

