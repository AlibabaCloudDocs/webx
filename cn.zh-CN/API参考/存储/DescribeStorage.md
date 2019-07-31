# DescribeStorage {#doc_api_WebPlus_DescribeStorage .reference}

调用DescribeStorage查询存储。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeStorage&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/storage HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|49C3DE38-ABA2-4369-BED2-CBD1D\*\*\*\*\*\*\*\*\*\*|请求ID

 |
|Storage| | |存储描述信息

 |
|BucketName|String|webplus-cn-shenzhen-s-5d01fab421e\*\*\*\*\*121\*\*\*\*\*|存储的bucket名称

 |
|CreateTime|Long|1560410804957|存储创建时间

 |
|UpdateTime|Long|1560410804957|存储最后更新时间

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/storage&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeStorageResponse>
    <Storage>
        <BucketName>webplus-cn-shenzhen-s-5d01f**********812105691</BucketName>
        <CreateTime>1560410804957</CreateTime>
        <UpdateTime>1560410804957</UpdateTime>
    </Storage>
    <Message>success</Message>
    <RequestId>F4558EDF-7AF1-45FF-A65A-454*****1C3E</RequestId>
    <Code>OK</Code>
</DescribeStorageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Storage":{
		"BucketName":"webplus-cn-shenzhen-s-5d01fab**********2105691",
		"CreateTime":1560410804957,
		"UpdateTime":1560410804957
	},
	"Message":"success",
	"RequestId":"76818DD9-BBD6-4E66-9D23-2ED8**********914",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

