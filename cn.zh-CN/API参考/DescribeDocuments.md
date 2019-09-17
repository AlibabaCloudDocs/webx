# DescribeDocuments {#doc_api_WebPlus_DescribeDocuments .reference}

调用DescribeDocuments查询文档。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeDocuments&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/paas/doc/docList HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Documents| | |文档列表信息

 |
|DefaultDocumentUrl|String|https://help.aliyun.com/document\_detail/1\*\*\*\*\*.html|默认文档地址

 |
|DocumentId|String|118222|文档ID

 |
|DocumentTitle|String|使用Web+部署您的第一个应用|文档标题

 |
|DocumentType|String|HelpDocument|文档类型

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|ECA5C3D2-597B-4E49-9858-80F1816\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/paas/doc/docList&<公共请求头>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDocumentsResponse>
    <Message>success</Message>
    <RequestId>59F91A78-5981-400A-9EB6-0C0A736*****</RequestId>
    <Documents>
        <Document>
            <DocumentId>118222</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/118222.html</DefaultDocumentUrl>
            <DocumentTitle>使用Web+部署您的第一个应用</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>160301</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/115432.html</DefaultDocumentUrl>
            <DocumentTitle>产品简介</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>116070</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/116070.html</DefaultDocumentUrl>
            <DocumentTitle>CLI使用文档</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>116518</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/116518.html</DefaultDocumentUrl>
            <DocumentTitle>如何配置您的部署环境</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>120264</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/120264.html</DefaultDocumentUrl>
            <DocumentTitle>常见问题与解答</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>119101</DocumentId>
            <DefaultDocumentUrl>https://help.aliyun.com/document_detail/119101.html</DefaultDocumentUrl>
            <DocumentTitle>如何提取应用运行日志</DocumentTitle>
            <DocumentType>HelpDocument</DocumentType>
        </Document>
        <Document>
            <DocumentId>54120468</DocumentId>
            <DefaultDocumentUrl>//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/console-create-env.mp4</DefaultDocumentUrl>
            <DocumentTitle>视频讲解：如何通过控制台创建应用及环境</DocumentTitle>
            <DocumentType>HelpVideo</DocumentType>
        </Document>
        <Document>
            <DocumentId>54120468</DocumentId>
            <DefaultDocumentUrl>//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/console-apply-configs.mp4</DefaultDocumentUrl>
            <DocumentTitle>视频讲解：如何通过控制台变更应用环境配置</DocumentTitle>
            <DocumentType>HelpVideo</DocumentType>
        </Document>
        <Document>
            <DocumentId>54120468</DocumentId>
            <DefaultDocumentUrl>//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-installation.mp4</DefaultDocumentUrl>
            <DocumentTitle>视频讲解：如何通过安装并配置命令行工具</DocumentTitle>
            <DocumentType>HelpVideo</DocumentType>
        </Document>
        <Document>
            <DocumentId>54120468</DocumentId>
            <DefaultDocumentUrl>//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-create-env.mp4</DefaultDocumentUrl>
            <DocumentTitle>视频讲解：如何使用命令行工具创建应用及环境</DocumentTitle>
            <DocumentType>HelpVideo</DocumentType>
        </Document>
        <Document>
            <DocumentId>54120468</DocumentId>
            <DefaultDocumentUrl>//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-apply-configs.mp4</DefaultDocumentUrl>
            <DocumentTitle>视频讲解：如何使用命令行工具变更应用环境配置</DocumentTitle>
            <DocumentType>HelpVideo</DocumentType>
        </Document>
    </Documents>
    <Code>OK</Code>
</DescribeDocumentsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"ECA5C3D2-597B-4E49-9858-80F1816*****",
	"Documents":{
		"Document":[
			{
				"DocumentId":"118222",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"使用Web+部署您的第一个应用",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"160301",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"产品简介",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"116070",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"CLI使用文档",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"116518",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"如何配置您的部署环境",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"120264",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"常见问题与解答",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"119101",
				"DefaultDocumentUrl":"https://help.aliyun.com/document_detail/1*****.html",
				"DocumentTitle":"如何提取应用运行日志",
				"DocumentType":"HelpDocument"
			},
			{
				"DocumentId":"54120468",
				"DefaultDocumentUrl":"//aliw*****z.oss-cn-shenzhen.aliyuncs.com/docs/videos/console-create-env.mp4",
				"DocumentTitle":"视频讲解：如何通过控制台创建应用及环境",
				"DocumentType":"HelpVideo"
			},
			{
				"DocumentId":"54120468",
				"DefaultDocumentUrl":"//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/console-apply-configs.mp4",
				"DocumentTitle":"视频讲解：如何通过控制台变更应用环境配置",
				"DocumentType":"HelpVideo"
			},
			{
				"DocumentId":"54120468",
				"DefaultDocumentUrl":"//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-installation.mp4",
				"DocumentTitle":"视频讲解：如何通过安装并配置命令行工具",
				"DocumentType":"HelpVideo"
			},
			{
				"DocumentId":"54120468",
				"DefaultDocumentUrl":"//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-create-env.mp4",
				"DocumentTitle":"视频讲解：如何使用命令行工具创建应用及环境",
				"DocumentType":"HelpVideo"
			},
			{
				"DocumentId":"54120468",
				"DefaultDocumentUrl":"//aliwebx-sz.oss-cn-shenzhen.aliyuncs.com/docs/videos/cli-apply-configs.mp4",
				"DocumentTitle":"视频讲解：如何使用命令行工具变更应用环境配置",
				"DocumentType":"HelpVideo"
			}
		]
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

