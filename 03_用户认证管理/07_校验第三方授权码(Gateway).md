
> 校验第三方授权码

校验第三方的授权码，并从第三方授权服务器，获取access_token。

####URL
<http://$AUTHSERVER/api/wifi_third_auth>

####支持格式
`JSON`

####Content-Type
`application/json`

####HTTP请求方式
`GET`

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
| as_type | true |    int | 具体指哪一个第三方: <br/> 1.腾讯 2.百度 3.新浪 4.网易 5.微信验证码 6.一键上网 7.微信粉丝 8.facebook 9.twitter 10.微信连wifi |
| redirect_url |    false |   string |  如果不是页面调用，且不需要重定向，则不需要此参数。 |
| access_token |    true |    string |  设备初始化后得到的网关密钥. <br/> 用于确认当前终端用户所属机构。 |


####注意事项
无

####请求消息内容
``` JSON
```
####返回结果
``` JSON
{"result":{
    "figureUrl":"NoAuthUser",
    "nickName":"NoAuthUser(00:f7:6f:b7:e4:51)",
    "groupRule":{
        "priority":1,
        "flowLimitM":10,
        "flowLimitD":10,
        "flowLimitT":10,
        "timeLimitM":10,
        "timeLimitD":10,
        "timeLimitT":10,
        "bandwidthTX":2,
        "bandwidthRX":2
    },
    "userId":"54816f140cf2a45a2b264e94",
    "gender":"NoAuthUser",
    "userTraffic":{
        "date":1420041600000,
        "userId":"54816f140cf2a45a2b264e94",
        "txM":77430,
        "rxM":229901,
        "timeM":600,
        "txD":430,
        "rxD":9901,
        "timeD":0,
        "interval":3275134,
        "_id":"54b369764b9e9ce1743512b6"
    }
    }
}

```
####返回值字段说明
| 返回值字段 | 字段类型 | 字段说明                |
| ---------- | --------:| :---------------------- |
| priority |    int |  网络优先级：1---high level,2---middle level,3---low level |
| flowLimitM |  int |  每月上网流量限制，单位：M/月 |
| flowLimitD |  int |  每天上网流量限制，单位：M/日 |
| flowLimitT |  int |  当次上网流量限制，单位：M |
| timeLimitM |  int |  每月上网时长限制，单位：分钟/月 |
| timeLimitD |  int |  每天上网时长限制，单位：分钟/日 |
| timeLimitT |  int |  当次上网时长限制，单位：分钟 |
| bandwidthTX |  int |  网速限制:上行，单位：KB/秒 |
| bandwidthRX |  int |  网速限制:下行，单位：KB/秒 |
| userTraffic |  Object |  用户流量使用数据对象 |
| date |  long |  时间戳 |
| userId |  ObjectId |  终端用户ID |
| txM |  int |  当前终端用户，当月上行流量|
| rxM |  int |  当前终端用户，当月下行流量 |
| timeM |  int |  当前终端用户，当月上网时长 |
| txD |  int |  当前终端用户，当日上行流量 |
| rxD |  int |  当前终端用户，当日下行流量 |
| timeD |  int |  当前终端用户，当日上网时长 |


####其他
无
