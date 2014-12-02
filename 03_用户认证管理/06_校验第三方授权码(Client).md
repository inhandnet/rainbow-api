
> 校验第三方授权码

校验第三方的授权码，并从第三方授权服务器，获取access_token。

####URL
<http://$AUTHSERVER/api/gateway/validate_code>

####支持格式
`JSON`

####Content-Type
`application/json`

####HTTP请求方式
`POST`

####是否需要登录
`否`

#### 访问授权限制
* 访问级别：[普通接口]
* 频次限制：[否]
* 访问权限：


####请求参数

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| client_id |   true |    string |  应用标识（appid） |
| client_secret |   true |    string |  应用密钥（appkey） |
| grant_type |  true |    string |  授权类型（一般固定值：authorization_code） |
| code |    true |    string |  第三方的授权码 |
| as_type | true |    int | 具体指哪一个第三方: <br/> 1.腾讯 2.百度 3.新浪 4.网易 |


####注意事项
无

####请求消息内容
``` JSON
```
####返回结果
``` JSON
{ 
    "access_token" : "LKASLAFAFAJLKJDSKLFDSF", 
    "expires_in" : 3600
}
```
####返回值字段说明
| 返回值字段 | 字段类型 | 字段说明                |
| ---------- | --------:| :---------------------- |
| access_token |    string |  第三方授予的token |
| expires_in |  string |  过期时间（秒） |

####其他
无
