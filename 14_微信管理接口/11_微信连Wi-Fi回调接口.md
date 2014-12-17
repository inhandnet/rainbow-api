
> 微信连Wi-Fi回调接口

####URL
<http://rainbow.inhand.com.cn/api/wifi/wechat>

####支持格式
`JSON`

####Content-Type
`application/json`

####HTTP请求方式
`GET`

####是否需要登录
`是`

#### 访问授权限制
* 访问级别: [普通接口]
* 频次限制: [否]
* 访问权限: 无


####请求参数

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| wxuid  | true    | string      | 微信用户openid |
| hasphone  | true    | string      | 是否已绑定手机号，是为"1",否为"-1" |
| lgnid  | false    | string      | 二维码参数，表示pc mac。 |
| ssid  | false    | string      | 当前连接的AP SSID |
| auth  | true    | string      | 认证信息，<br/>"{deviceId}-{mac}-{time}-{md5({deviceId}-{mac}-{time}-{deviceKey})"|
| signature  | true    | string      | 微信消息签名 |
| timestamp  | true    | string      | 时间戳 |
| nonce  | true    | string      | 随机数 |
| echostr  | true    | string      | 微信需要的返回值 |

####注意事项
无

####请求消息内容
``` JSON
无
```

####返回结果
``` JSON
{
	"state": "0",
	"login": "",
	"logout" : "http://192.168.60.1:3990/logoff",
	"device_no" : "123321",
	"store_name" : "广州 T.I.T 时尚咖啡",
	"store_id": "320123",
	"client_mac" : "84-3A-4B-DC-39-B8",
	"addition_mac" : "84-3A-4B-DC-39-B9",
	"login_state" : 0,
	"login_remain" : 1208,
	"login_allow" : 1010,
	"echostr": "",
	"reason": ""
}
```
####返回值字段说明
| 返回值字段 | 字段类型 | 字段说明                |
| ---------- | --------:| :---------------------- |
| state | string  | 0表示成功，-1表示服务器内部错误，-2表示lgnid对应设备验证未通过 |
| login | string  | 登录请求url |
| logout | string  | 登出请求url |
| device_no | string  | 设备序列号 |
| store_name | string  | 现场名称 |
| store_id | string  | 现场标识 |
| client_mac | string  | 手机MAC |
| addition_mac | string  | PC MAC或者PAD MAC |
| login_state | string  | 用户现在的登录状态，0表示已登录，-1表示未登录 |
| login_remain | string  | 单位秒。用户上次连接剩余上网时间（不会有小于 0 的情况） |
| login_allow | string  | 单位秒。此次认证通过的新增允许上网时间。 |
| echostr | string  | 请求参数里的echostr |
| reason | string | 错误原因，当state非"0"时需要 |

####其他
无
