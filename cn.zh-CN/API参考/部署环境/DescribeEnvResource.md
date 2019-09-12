# DescribeEnvResource {#doc_api_WebPlus_DescribeEnvResource .reference}

调用DescribeEnvResource查询一个环境内的所有资源。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=DescribeEnvResource&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/wam/envResource HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|是|we-5d22f93dcd04d705b65\*\*\*\*\*|环境ID，将查询此环境内的所有资源

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|EnvResource| | |环境资源信息

 |
|DefaultSecurityGroups| | |环境的默认安全组信息

 |
|SecurityGroup| | |环境的默认安全组信息

 |
|Id|String|sg-5d22f93dcd04d705b65\*\*\*\*\*|安全组ID

 |
|EnvId|String|we-5d22f93dcd04d705b65\*\*\*\*\*|环境ID

 |
|EnvName|String|test1|环境名称

 |
|Instances| | |环境内ECS实例信息列表

 |
|Instance| | |环境内ECS实例信息列表

 |
|Id|String|i-wz9ci3y5rx4ub93\*\*\*\*\*|实例ID

 |
|Imported|Boolean|false|是否为导入实例

 |
|LaunchConfigurationId|String|""|启动配置ID

 |
|LaunchTemplateId|String|""|启动模版ID

 |
|LoadBalancers| | |环境内负载均衡资源列表

 |
|LoadBalancer| | |环境内负载均衡资源列表

 |
|AddressType|String|""|地址类型

 |
|Id|String|""|负载均衡实例ID

 |
|Imported|Boolean|false|是否为导入实例

 |
|Port|Integer|1001|端口号

 |
|Protocol|String|""|协议

 |
|MonitorGroup| | |资源监控组

 |
|Id|String|71\*\*\*\*\*|监控组ID

 |
|RdsInstances| | |环境内RDS实例信息

 |
|RdsInstance| | |环境内RDS实例信息

 |
|AccountName|String|webplus|数据库账号名

 |
|DatabaseName|String|webplus|数据库名

 |
|Id|String|rm-5d22f93dcd04d705b65\*\*\*\*\*|RDS实例ID

 |
|Imported|Boolean|false|是否为导入实例

 |
|ScalingGroup| | |弹性伸缩组

 |
|Id|String|asg-wz9aaa7g5ff6fiw\*\*\*\*\*|弹性伸缩组ID

 |
|VSwitches| | |交换机列表

 |
|VSwitch| | |交换机列表

 |
|Id|String|vsw-wz9gfawx1vxkimtj\*\*\*\*\*|交换机ID

 |
|Vpc| | |VPC信息

 |
|Id|String|vpc-wz9e6y22o3o91nuy\*\*\*\*\*|VPC的ID

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|71CC3AA5-17C9-465F-8F8A-0B6BE58\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/envResource?ServiceCode=webx&EnvId=we-5d244085f314934e2ab*****&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeEnvResourceResponse>
    <Message>success</Message>
    <EnvResource>
        <Vpc>
            <Id>vpc-wz9e6y22o3o91nuy*****</Id>
        </Vpc>
        <VSwitches>
            <VSwitch>
                <Id>vsw-wz9gfawx1vxkimtj*****</Id>
            </VSwitch>
        </VSwitches>
        <MonitorGroup>
            <Id>71*****</Id>
        </MonitorGroup>
        <EnvName>test1</EnvName>
        <EnvId>we-5d22f93dcd04d705b65*****</EnvId>
        <ScalingGroup>
            <Id>asg-wz9aaa7g5ff6fiw*****</Id>
        </ScalingGroup>
        <LoadBalancers></LoadBalancers>
        <Instances>
            <Instance>
                <Id>i-wz9ci3y5rx4ub93*****</Id>
            </Instance>
        </Instances>
        <DefaultSecurityGroups>
            <SecurityGroup>
                <Id>sg-wz9b6zjhne81unz*****</Id>
            </SecurityGroup>
        </DefaultSecurityGroups>
        <RdsInstances></RdsInstances>
    </EnvResource>
    <RequestId>CA14B31B-4408-4B97-AB1E-78CECC5*****</RequestId>
    <Code>OK</Code>
</DescribeEnvResourceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"EnvResource":{
		"Vpc":{
			"Id":"vpc-wz9e6y22o3o91nuy*****"
		},
		"VSwitches":{
			"VSwitch":[
				{
					"Id":"vsw-wz9gfawx1vxkimtj*****"
				}
			]
		},
		"MonitorGroup":{
			"Id":"71*****"
		},
		"EnvName":"test1",
		"DefaultSecurityGroups":{
			"SecurityGroup":[
				{
					"Id":"sg-wz9b6zjhne81unz*****"
				}
			]
		},
		"EnvId":"we-5d22f93dcd04d705b65*****",
		"ScalingGroup":{
			"Id":"asg-wz9aaa7g5ff6fiw*****"
		},
		"LoadBalancers":{
			"LoadBalancer":[]
		},
		"Instances":{
			"Instance":[
				{
					"Imported":"false",
					"Id":"i-wz9ci3y5rx4ub93*****"
				}
			]
		},
		"RdsInstances":[]
	},
	"RequestId":"71CC3AA5-17C9-465F-8F8A-0B6BE58*****",
	"Code":"OK"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|ResourceAuthFailed|The specified resource does not exist or it does not belong to this Alibaba Cloud account.|相关资源不存在或不属于此阿里云账号。|

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

