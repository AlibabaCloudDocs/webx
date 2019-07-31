# ValidateConfigSetting {#doc_api_WebPlus_ValidateConfigSetting .reference}

调用ValidateConfigSetting来验证一个配置的设置有效性。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=WebPlus&api=ValidateConfigSetting&type=ROA&version=2019-03-20)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
POST /pop/v1/wam/config/configSetting/validate HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EnvId|String|否|we-5d3eaaea2977ca5251e\*\*\*\*\*|环境ID

 |
|OptionSettings|String|否|\[\{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"\}, \{"path":"application.option", "name":"port","value":"100"\}\]|自定义配置项数据，JSON数组，包含以下字段：

 -   `path`：配置项路径
-   `name`：配置项名称
-   `value`：配置值

 |
|StackId|String|否|ws-6c937c98a9c0296d0c48\*\*\*\*\*|栈ID

 |
|TemplateId|String|否|wct-5d3e9d2a2977ca5251e\*\*\*\*\*|配置模板ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|响应代码，若成功请求为OK

 |
|ConfigValidationResults| | |配置有效性验证结果

 |
|ConfigOption| | |配置可选项

 |
|ChangeSeverity|String|NoInterruption|变更重要性

 |
|DefaultValue|String|8080|默认值

 |
|EditorType|String|\{\\"component\\":\\"NumberPicker\\",\\"props\\":\{\}\}|编辑类型

 |
|HiddenOption|Boolean|false|是否为隐藏选项

 |
|MaxLength|Integer|-1|最大长度

 |
|MaxValue|Long|65535|最大值

 |
|MinLength|Integer|0|最小长度

 |
|MinValue|Long|1024|最小值

 |
|OptionDescription|String|This port will be used as the HTTP service port after the application is launched, and ports from 1024 to 65535 can be used.|可选项描述信息

 |
|OptionLabel|String|Server Port|可选项标签

 |
|OptionName|String|port|可选项名称

 |
|PathName|String|application.option|路径名称

 |
|ReadonlyOption|Boolean|false|是否为只读选项

 |
|RegexDesc|String|""|正则匹配描述

 |
|RegexPattern|String|""|正则匹配模式

 |
|ValueOptions|String|""|值可选项

 |
|ValueType|String|Integer|值类型

 |
|OptionName|String|port|选项名称

 |
|PathName|String|application.option|路径名称

 |
|ResultMessage|String|Parsing configuration values fails. Please make sure the value is consistent with the declared type. Currently supported types are: String, Integer, List, Boolean, Float, Json.|结果信息

 |
|ResultSeverity|String|Error|结果重要性

 |
|Message|String|success|响应消息，若成功请求为success

 |
|RequestId|String|170E6BDE-8ACA-4013-B1D6-F0C2AAD\*\*\*\*\*|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http://webplus.cn-hangzhou.aliyuncs.com/pop/v1/wam/config/configSetting/validate&<公共请求头>
{
  "EnvId":"we-5d3eaaea2977ca5251e*****",
  "TemplateId":"wct-5d3e9d2a2977ca5251e*****",
  "StackId":"ws-6c937c98a9c0296d0c48*****",
  "OptionSettings":"[{"path":"resources.ecs.autoScaling", "name":"instanceNum","value":"10"},     {"path":"application.option", "name":"port","value":"100"}]"
}

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ValidateConfigSettingResponse>
    <ConfigValidationResults>
        <ConfigValidationResult>
            <ResultSeverity>Error</ResultSeverity>
            <ConfigOption>
                <MinValue>1024</MinValue>
                <ValueType>Integer</ValueType>
                <RegexPattern></RegexPattern>
                <EditorType>{"component":"NumberPicker","props":{}}</EditorType>
                <DefaultValue>8080</DefaultValue>
                <MaxValue>65535</MaxValue>
                <RegexDesc></RegexDesc>
                <PathName>application.option</PathName>
                <OptionName>port</OptionName>
                <OptionLabel>Server Port</OptionLabel>
                <ChangeSeverity>NoInterruption</ChangeSeverity>
                <ReadonlyOption>false</ReadonlyOption>
                <MaxLength>-1</MaxLength>
                <ValueOptions></ValueOptions>
                <HiddenOption>false</HiddenOption>
                <MinLength>0</MinLength>
                <OptionDescription>This port will be used as the HTTP service port after the application is launched, and ports from 1024 to 65535 can be used.</OptionDescription>
            </ConfigOption>
            <ResultMessage>Parsing configuration values fails. Please make sure the value is consistent with the declared type. Currently supported types are: String, Integer, List, Boolean, Float, Json.</ResultMessage>
            <PathName>application.option</PathName>
            <OptionName>port</OptionName>
        </ConfigValidationResult>
    </ConfigValidationResults>
    <Message>success</Message>
    <RequestId>6112EBD9-E35E-4D98-91D5-5E302F7*****</RequestId>
    <Code>OK</Code>
</ValidateConfigSettingResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"ConfigValidationResults":{
		"ConfigValidationResult":[
			{
				"ResultSeverity":"Error",
				"ConfigOption":{
					"MinValue":1024,
					"ValueType":"Integer",
					"RegexPattern":"",
					"EditorType":"{\"component\":\"NumberPicker\",\"props\":{}}",
					"DefaultValue":"8080",
					"RegexDesc":"",
					"MaxValue":65535,
					"PathName":"application.option",
					"OptionName":"port",
					"OptionLabel":"Server Port",
					"ChangeSeverity":"NoInterruption",
					"ReadonlyOption":false,
					"MaxLength":-1,
					"ValueOptions":"",
					"HiddenOption":false,
					"MinLength":0,
					"OptionDescription":"This port will be used as the HTTP service port after the application is launched, and ports from 1024 to 65535 can be used."
				},
				"ResultMessage":"Parsing configuration values fails. Please make sure the value is consistent with the declared type. Currently supported types are: String, Integer, List, Boolean, Float, Json.",
				"PathName":"application.option",
				"OptionName":"port"
			}
		]
	},
	"Message":"success",
	"RequestId":"170E6BDE-8ACA-4013-B1D6-F0C2AAD*****",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/WebPlus)查看更多错误码。

