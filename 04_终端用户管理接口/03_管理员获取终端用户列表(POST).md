
> 管理员获取终端用户列表

####URL
<http://$AUTHSERVER/api/wifi_user>

####支持格式
`JSON`

####Content-Type
`application/json`

####HTTP请求方式
`POST`

####是否需要登录
`是`

#### 访问授权限制
* 访问级别: [普通接口]
* 频次限制: [否]
* 访问权限: ReadWifiUser


####请求参数

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| access_token  | true    | string      | OAuth授权后获得。</br>注：通过HTTP认证头携带时省略。 |
| verbose | false   | int | 信息详细级别。 |
| oid | false   | string |  机构标识。仅系统用户在调用时可以指定，默认为与access_token关联的用户所属机构相同。 |

####注意事项
无

####请求消息内容
``` JSON
{
    "resourceIds": ["09850345", "0938534", ...]
}
```

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| resourceIds | true |  string array |    终端用户标识数组。 |


####返回结果
``` JSON
{
    "total": 10,
    "cursor": 3,
    "limit": 2,
    "result": [$WifiUserInfo,...]
}

```
####返回值字段说明
| 返回值字段 | 字段类型 | 字段说明                |
| ---------- | --------:| :---------------------- |
| total |   int | 结果总数。 |
| cursor |  int | 游标。表示从结果的第几条开始。 |
| limit |   int | 返回的结果数目。 |
| result |  object array | 返回的终端用户对象 |
| $WifiUserInfo  | object |  终端用户信息 |


####其他
无
