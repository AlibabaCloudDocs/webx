# AbortChange {#doc_api_WebPlus_AbortChange .reference}

使用AbortChange可以中止一次变更。

-   当此API调用后，Web+会等待正在进行的变更步骤执行完毕后再停止变更。
-   当环境有变更正在被终止时，不可重复调用此接口。
-   变更在中止后不可恢复执行。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=AbortChange&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/change/abort HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChangeId|String|是|wc-5d3a963d5802611c4ddc\*\*\*\*|变更ID，将中止此变更

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvChange| | |被中止的变更信息

 |
|ChangeId|String|wc-5cdbd6d884b53b4bc95\*\*\*\*\*|变更ID

 |
|EnvId|String|we-5d39b8ba6786bd4b149\*\*\*\*\*|环境ID

 |
|StartTime|String|1557911256210|该变更的开始执行时间戳

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|14A65FB3-DFD6-4D9A-83EA-9259C2D3\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com&<公共请求参数>
{
  "ChangeId":"wc-5cda75398047880ad2c8****"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AbortChangeResponse>
    <Message>success</Message>
    <EnvChange>
        <ChangeId>wc-5cdbd79a84b53b4bc958****</ChangeId>
        <EnvId>we-5cdbd64084b53b4bc958****</EnvId>
        <StartTime>1557911450434</StartTime>
    </EnvChange>
    <RequestId>BED39BFD-3CBF-42F0-9711-C91E32BF****</RequestId>
    <Code>OK</Code>
</AbortChangeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"3A6ECBAB-4A14-4412-AFE7-6B75D55A****",
	"EnvChange":{
		"EnvId":"we-5cdbd64084b53b4bc958****",
		"ChangeId":"wc-5cdbd6d884b53b4bc958****",
		"StartTime":1557911256210
	},
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|
|400|ChangeOnAborting|The change is being canceled. Please do not cancel again.|变更正在被中止，请勿重复操作。|
|400|ChangeFinished|An error occurred while stopping the change. The change is already complete.|放弃变更失败，因为此次变更已经完成。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

