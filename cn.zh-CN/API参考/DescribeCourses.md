# DescribeCourses {#doc_api_WebPlus_DescribeCourses .reference}

调用DescribeCourses查询教程信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeCourses&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/paas/course/courseList HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|Courses| | |教程信息列表

 |
|CourseFileName|String|startdemo.md|教程文件名

 |
|CourseSummary|String|Web+ 支持您的源码工程与某一个部署环境进行绑定，绑定之后，您可以随时通过命令行工具将源码工作目录与部署环境之间进行联动，包括应用生命周期管理、监控、日志下载等功能。\\n本示例将以 Demo 工程为例，向您展示这些功能。|教程概括

 |
|CourseTitle|String|如何从 Java 源码开始部署至 Web+|教程标题

 |
|GitUrl|String|""|教程的git链接

 |
|MdUrl|String|http://ali\*\*\*\*\*.oss-cn-shenzhen.aliyuncs.com/docs/course/startdemo.md|教程的md文本链接

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|4E5F7AB2-B013-4CE3-A611-4A8CE8DD\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/paas/course/courseList&<公共请求头>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCoursesResponse>
    <Message>success</Message>
    <RequestId>4419DFD2-1D35-4250-AF57-2D6627C*****</RequestId>
    <Courses>
        <Course>
            <CourseFileName>startdemo.md</CourseFileName>
            <GitUrl></GitUrl>
            <CourseSummary>Web+ 支持您的源码工程与某一个部署环境进行绑定，绑定之后，您可以随时通过命令行工具将源码工作目录与部署环境之间进行联动，包括应用生命周期管理、监控、日志下载等功能。
本示例将以 Demo 工程为例，向您展示这些功能。</CourseSummary>
            <MdUrl>http://al*****-sz.oss-cn-shenzhen.aliyuncs.com/docs/course/startdemo.md</MdUrl>
            <CourseTitle>如何从 Java 源码开始部署至 Web+</CourseTitle>
        </Course>
        <Course>
            <CourseFileName>jenkins.md</CourseFileName>
            <GitUrl></GitUrl>
            <CourseSummary>Jenkins 是一个基于 Java 语言开发的持续集成开源软件工具，在使用持续集成开发模式的项目中广泛使用。此教程将向您展示如何基于 Web+ 的官方 Jenkins 模版，使用命令行工具一键拉起一套全新独享的 Jenkins 环境。</CourseSummary>
            <MdUrl>http://al*****-sz.oss-cn-shenzhen.aliyuncs.com/docs/course/jenkins.md</MdUrl>
            <CourseTitle>基于 Web+ 模版一键生成一套 Jenkins 环境</CourseTitle>
        </Course>
        <Course>
            <CourseFileName>wikijs.md</CourseFileName>
            <GitUrl></GitUrl>
            <CourseSummary>Wiki.js 是一个 NodeJS 开源的博客系统，是 PHP 语言的 WordPress 的一个强有力的挑战者，功能强大、界面清爽、默认提供了程序员喜欢的 Markdown 编辑器、搭建也及其简单，加上 JavaScript 语言的蓬勃发展。使得 Wiki.js 在 CMS 领域越来越受欢迎。
本篇教程，着重介绍如何在 WebPlus 中方便的拉起一套 Wiki.js 应用程序(版本：2.0.0-beta.241)。</CourseSummary>
            <MdUrl>http://a*****-sz.oss-cn-shenzhen.aliyuncs.com/docs/course/wikijs.md</MdUrl>
            <CourseTitle>搭建 NodeJS 版本的博客系统：Wiki.js</CourseTitle>
        </Course>
    </Courses>
    <Code>OK</Code>
</DescribeCoursesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"4E5F7AB2-B013-4CE3-A611-4A8CE8D*****",
	"Courses":{
		"Course":[
			{
				"CourseFileName":"startdemo.md",
				"GitUrl":"",
				"CourseSummary":"Web+ 支持您的源码工程与某一个部署环境进行绑定，绑定之后，您可以随时通过命令行工具将源码工作目录与部署环境之间进行联动，包括应用生命周期管理、监控、日志下载等功能。\n本示例将以 Demo 工程为例，向您展示这些功能。",
				"MdUrl":"http://aliw*****.oss-cn-shenzhen.aliyuncs.com/docs/course/startdemo.md",
				"CourseTitle":"如何从 Java 源码开始部署至 Web+"
			},
			{
				"CourseFileName":"jenkins.md",
				"GitUrl":"",
				"CourseSummary":"Jenkins 是一个基于 Java 语言开发的持续集成开源软件工具，在使用持续集成开发模式的项目中广泛使用。此教程将向您展示如何基于 Web+ 的官方 Jenkins 模版，使用命令行工具一键拉起一套全新独享的 Jenkins 环境。",
				"MdUrl":"http://aliw*****.oss-cn-shenzhen.aliyuncs.com/docs/course/jenkins.md",
				"CourseTitle":"基于 Web+ 模版一键生成一套 Jenkins 环境"
			},
			{
				"CourseFileName":"wikijs.md",
				"GitUrl":"",
				"CourseSummary":"Wiki.js 是一个 NodeJS 开源的博客系统，是 PHP 语言的 WordPress 的一个强有力的挑战者，功能强大、界面清爽、默认提供了程序员喜欢的 Markdown 编辑器、搭建也及其简单，加上 JavaScript 语言的蓬勃发展。使得 Wiki.js 在 CMS 领域越来越受欢迎。\n本篇教程，着重介绍如何在 WebPlus 中方便的拉起一套 Wiki.js 应用程序(版本：2.0.0-beta.241)。",
				"MdUrl":"http://ali*****.oss-cn-shenzhen.aliyuncs.com/docs/course/wikijs.md",
				"CourseTitle":"搭建 NodeJS 版本的博客系统：Wiki.js"
			}
		]
	},
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

