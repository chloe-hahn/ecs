# DeleteSecurityGroup {#doc_api_Ecs_DeleteSecurityGroup .reference}

调用DeleteSecurityGroup删除一个安全组。删除安全组之前，请确保安全组内不存在实例，并且没有其他安全组与该安全组有授权行为（DescribeSecurityGroupReferences），否则 DeleteSecurityGroup 请求失败。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Ecs&api=DeleteSecurityGroup)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|地域 ID。您可以调用 [DescribeRegions](~~25609~~) 查看最新的阿里云地域列表。

 |
|SecurityGroupId|String|是|sg-securitygroupid1|安全组 ID。

 |
|Action|String|否|DeleteSecurityGroup|系统规定参数。取值：DeleteSecurityGroup

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E|请求 ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://ecs.aliyuncs.com/?Action=DeleteSecurityGroup
&RegionId=cn-hangzhou
&SecurityGroupId=sg-F876FF7**
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteSecurityGroupResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</DeleteSecurityGroupResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|DependencyViolation|There is still instance\(s\) in the specified security group.|安全组中还有未释放的实例，请您先释放实例再进行该操作。|
|403|DependencyViolation|The specified security group has been authorized in another one.|指定的安全组已在另一个组中授权，不允许重复授权。|

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

