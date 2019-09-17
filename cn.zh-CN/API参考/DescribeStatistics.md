# DescribeStatistics {#doc_api_WebPlus_DescribeStatistics .reference}

调用DescribeStatistics查询统计信息，可查询应用个数、实例个数、环境个数等信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeStatistics&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/statistics HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|8F0BD24D-0CDF-40F4-952C-B8F35C2\*\*\*\*\*|请求ID

 |
|Statistics| | |统计信息

 |
|TotalAppEnvs|Integer|35|总环境个数

 |
|TotalApplications|Integer|22|总应用个数

 |
|TotalInstances|Integer|1|总实例个数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/statistics&公共请求头

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeStatisticsResponse>
    <Statistics>
        <TotalAppEnvs>35</TotalAppEnvs>
        <TotalInstances>1</TotalInstances>
        <TotalApplications>22</TotalApplications>
    </Statistics>
    <Message>success</Message>
    <RequestId>A4202DD5-D716-48AB-B36C-327626A*****</RequestId>
    <Code>OK</Code>
</DescribeStatisticsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Statistics":{
		"TotalAppEnvs":35,
		"TotalInstances":1,
		"TotalApplications":22
	},
	"Message":"success",
	"RequestId":"8F0BD24D-0CDF-40F4-952C-B8F35C2*****",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

