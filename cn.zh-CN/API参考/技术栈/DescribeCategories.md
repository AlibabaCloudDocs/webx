# DescribeCategories {#doc_api_WebPlus_DescribeCategories .reference}

调用DescribeCategories查询平台类型。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeCategories&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/category HTTP/1.1
```

## 请求参数 {#parameters .section}

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Categories| | |平台类型查询结果

 |
|CategoryDescription|String|Use Tomcat as an application container, support for WAR or ZIP type application deployment packages.|类型描述信息

 |
|CategoryId|String|wca-5c937c98a9c0296d0c4823912|类型ID

 |
|CategoryLogo|String|http://tomcat.apache.org/res/images/tomcat.png|类型LOGO

 |
|CategoryName|String|Tomcat|类型名称

 |
|CreateTime|String|1553218065000|平台类型创建时间

 |
|DemoProjects| | |样例项目

 |
|PackageUrl|String|oss://webplus-prod-cn-shenzhen/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war|资源包URL地址

 |
|RegionId|String|cn-shenzhen|环境所在地域

 |
|SourceUrl|String|https://github.com/aliyun/alibabacloud-webplus-demo-tomcat|源码地址

 |
|UpdateTime|String|1553218065000|平台类型更新时间

 |
|Code|String|OK|响应代码，若成功请求为OK

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|6E99F8E3-7493-4ADA-A27B-2DFF2C693555|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/category?ServiceCode=webx&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCategoriesResponse>
    <Message>success</Message>
    <RequestId>2EF90744-064A-4841-B9E3-6B0D7AE6785A</RequestId>
    <Code>OK</Code>
    <Categories>
        <Category>
            <CategoryName>Tomcat</CategoryName>
            <CategoryId>wca-5c937c98a9c0296d0c4823912</CategoryId>
            <CategoryDescription>Use Tomcat as an application container, support for WAR or ZIP type application deployment packages.</CategoryDescription>
            <DemoProjects>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-tomcat-demo</SourceUrl>
                    <RegionId>cn-shenzhen</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shenzhen/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-tomcat-demo</SourceUrl>
                    <RegionId>cn-zhangjiakou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-zhangjiakou/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-tomcat-demo</SourceUrl>
                    <RegionId>cn-beijing</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-beijing/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-tomcat-demo</SourceUrl>
                    <RegionId>cn-shanghai</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shanghai/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-tomcat-demo</SourceUrl>
                    <RegionId>cn-hangzhou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-hangzhou/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war</PackageUrl>
                </DemoProject>
            </DemoProjects>
            <CategoryLogo>http://tomcat.apache.org/res/images/tomcat.png</CategoryLogo>
            <CreateTime>1553218065000</CreateTime>
            <UpdateTime>1553218065000</UpdateTime>
        </Category>
        <Category>
            <CategoryName>Java</CategoryName>
            <CategoryId>wca-6c937c98a9c0296d0c4823912</CategoryId>
            <CategoryDescription>Direct startup using Java commands, support for FatJAR or ZIP type application deployment packages.</CategoryDescription>
            <DemoProjects>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-java-demo</SourceUrl>
                    <RegionId>cn-shenzhen</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shenzhen/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-java-demo</SourceUrl>
                    <RegionId>cn-zhangjiakou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-zhangjiakou/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-java-demo</SourceUrl>
                    <RegionId>cn-beijing</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-beijing/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-java-demo</SourceUrl>
                    <RegionId>cn-shanghai</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shanghai/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-java-demo</SourceUrl>
                    <RegionId>cn-hangzhou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-hangzhou/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar</PackageUrl>
                </DemoProject>
            </DemoProjects>
            <CategoryLogo>https://openjdk.java.net/images/duke-thinking.png</CategoryLogo>
            <CreateTime>1553218065000</CreateTime>
            <UpdateTime>1553218065000</UpdateTime>
        </Category>
        <Category>
            <CategoryName>Node.js</CategoryName>
            <CategoryId>wca-7c937c98a9c0296d0c4823912</CategoryId>
            <CategoryDescription>The Node.js application supports ZIP-type application deployment packages.</CategoryDescription>
            <DemoProjects>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-node-demo</SourceUrl>
                    <RegionId>cn-shenzhen</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shenzhen/quickstart/node/first-step/webplus-node-demo-0.1.0.zip</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-node-demo</SourceUrl>
                    <RegionId>cn-zhangjiakou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-zhangjiakou/quickstart/node/first-step/webplus-node-demo-0.1.0.zip</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-node-demo</SourceUrl>
                    <RegionId>cn-beijing</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-beijing/quickstart/node/first-step/webplus-node-demo-0.1.0.zip</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-node-demo</SourceUrl>
                    <RegionId>cn-shanghai</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-shanghai/quickstart/node/first-step/webplus-node-demo-0.1.0.zip</PackageUrl>
                </DemoProject>
                <DemoProject>
                    <SourceUrl>https://github.com/aliyun/alibabacloud-webplus-node-demo</SourceUrl>
                    <RegionId>cn-hangzhou</RegionId>
                    <PackageUrl>oss://webplus-prod-cn-hangzhou/quickstart/node/first-step/webplus-node-demo-0.1.0.zip</PackageUrl>
                </DemoProject>
            </DemoProjects>
            <CategoryLogo>http://tomcat.apache.org/res/images/tomcat.png</CategoryLogo>
            <CreateTime>1553218065000</CreateTime>
            <UpdateTime>1553218065000</UpdateTime>
        </Category>
    </Categories>
</DescribeCategoriesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"20A72DF0-F63D-4763-BBCA-1999AAA9693D",
	"Code":"OK",
	"Categories":{
		"Category":[
			{
				"CategoryName":"Tomcat",
				"CategoryId":"wca-5c937c98a9c0296d0c4823912",
				"CategoryDescription":"Use Tomcat as an application container, support for WAR or ZIP type application deployment packages.",
				"DemoProjects":{
					"DemoProject":[
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-tomcat-demo",
							"RegionId":"cn-shenzhen",
							"PackageUrl":"oss://webplus-prod-cn-shenzhen/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-tomcat-demo",
							"RegionId":"cn-zhangjiakou",
							"PackageUrl":"oss://webplus-prod-cn-zhangjiakou/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-tomcat-demo",
							"RegionId":"cn-beijing",
							"PackageUrl":"oss://webplus-prod-cn-beijing/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-tomcat-demo",
							"RegionId":"cn-shanghai",
							"PackageUrl":"oss://webplus-prod-cn-shanghai/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-tomcat-demo",
							"RegionId":"cn-hangzhou",
							"PackageUrl":"oss://webplus-prod-cn-hangzhou/quickstart/tomcat/first-step/webplus-tomcat-demo-0.1.1.war"
						}
					]
				},
				"CategoryLogo":"http://tomcat.apache.org/res/images/tomcat.png",
				"CreateTime":1553218065000,
				"UpdateTime":1553218065000
			},
			{
				"CategoryName":"Java",
				"CategoryId":"wca-6c937c98a9c0296d0c4823912",
				"CategoryDescription":"Direct startup using Java commands, support for FatJAR or ZIP type application deployment packages.",
				"DemoProjects":{
					"DemoProject":[
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-java-demo",
							"RegionId":"cn-shenzhen",
							"PackageUrl":"oss://webplus-prod-cn-shenzhen/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-java-demo",
							"RegionId":"cn-zhangjiakou",
							"PackageUrl":"oss://webplus-prod-cn-zhangjiakou/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-java-demo",
							"RegionId":"cn-beijing",
							"PackageUrl":"oss://webplus-prod-cn-beijing/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-java-demo",
							"RegionId":"cn-shanghai",
							"PackageUrl":"oss://webplus-prod-cn-shanghai/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-java-demo",
							"RegionId":"cn-hangzhou",
							"PackageUrl":"oss://webplus-prod-cn-hangzhou/quickstart/java/first-step/webplus-java-demo-0.1.1-exec.jar"
						}
					]
				},
				"CategoryLogo":"https://openjdk.java.net/images/duke-thinking.png",
				"CreateTime":1553218065000,
				"UpdateTime":1553218065000
			},
			{
				"CategoryName":"Node.js",
				"CategoryId":"wca-7c937c98a9c0296d0c4823912",
				"CategoryDescription":"The Node.js application supports ZIP-type application deployment packages.",
				"DemoProjects":{
					"DemoProject":[
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-node-demo",
							"RegionId":"cn-shenzhen",
							"PackageUrl":"oss://webplus-prod-cn-shenzhen/quickstart/node/first-step/webplus-node-demo-0.1.0.zip"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-node-demo",
							"RegionId":"cn-zhangjiakou",
							"PackageUrl":"oss://webplus-prod-cn-zhangjiakou/quickstart/node/first-step/webplus-node-demo-0.1.0.zip"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-node-demo",
							"RegionId":"cn-beijing",
							"PackageUrl":"oss://webplus-prod-cn-beijing/quickstart/node/first-step/webplus-node-demo-0.1.0.zip"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-node-demo",
							"RegionId":"cn-shanghai",
							"PackageUrl":"oss://webplus-prod-cn-shanghai/quickstart/node/first-step/webplus-node-demo-0.1.0.zip"
						},
						{
							"SourceUrl":"https://github.com/aliyun/alibabacloud-webplus-node-demo",
							"RegionId":"cn-hangzhou",
							"PackageUrl":"oss://webplus-prod-cn-hangzhou/quickstart/node/first-step/webplus-node-demo-0.1.0.zip"
						}
					]
				},
				"CategoryLogo":"http://tomcat.apache.org/res/images/tomcat.png",
				"CreateTime":1553218065000,
				"UpdateTime":1553218065000
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

