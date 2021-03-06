# CreateCertAndKey {#doc_api_waf-openapi_CreateCertAndKey .reference}

调用CreateCertAndKey接口为已添加的域名配置记录上传证书及私钥信息。

**说明：** 您也可以调用该接口为指定域名配置更新已上传的证书及私钥信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=waf-openapi&api=CreateCertAndKey)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateCertAndKey|要执行的操作。取值：**CreateCertAndKey**。

 |
|Cert|String|是|-----BEGIN CERTIFICATE----------END CERTIFICATE-----|证书文件内容。

 |
|Domain|String|是|rstest.cdn.com|域名名称。

 |
|HttpsCertName|String|是|www.aliyun.com|证书名称。

 |
|InstanceId|String|是|waf\_elasticity-cn-0xldbqtm005|WAF实例ID。

 **说明：** 您可以通过调用[DescribePayInfo](~~86651~~)接口查看您当前WAF实例ID。

 |
|Key|String|是|-----BEGIN RSA PRIVATE KEY----------END RSA PRIVATE KEY-----|私钥文件内容

 |
|Region|String|否|cn|WAF实例所在的地域。取值：

 -   **cn**：表示中国大陆地区（默认）
-   **cn-hongkong**：表示海外地区

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|D7861F61-5B61-46CE-A47C-6B19160D5EB0|请求ID。

 |
|Result| | |返回结果。

 |
|└Status|Integer|2|请求执行状态：

 -   **0**：表示该请求等待执行。
-   **1**：表示该请求正在执行中。
-   **2**：表示该请求已执行完成。

 |
|└WafTaskId|String|aliyun.waf.20180712214032277.qmxI9a|WAF的请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://wafopenapi.cn-hangzhou.aliyuncs.com/?Action=DeleteDomainConfig
&Domain=www.aliyun.com
&Cert="-----BEGIN CERTIFICATE----------END CERTIFICATE-----"
&Key="-----BEGIN RSA PRIVATE KEY----------END RSA PRIVATE KEY-----"
&HttpsCertName=www.aliyun.com
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCertAndKeyResponse>
  <RequestId>D7861F61-5B61-46CE-A47C-6B19160D5EB0</RequestId>
  <Result>
    <Status>2</Status>
    <WafTaskId>aliyun.waf.20180712214032277.qmxI9a</WafTaskId>
  </Result>
</CreateCertAndKeyResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Result":{
		"Status":2,
		"WafTaskId":"aliyun.waf.20180712214032277.qmxI9a"
	},
	"RequestId":"D7861F61-5B61-46CE-A47C-6B19160D5EB0"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/waf-openapi)

