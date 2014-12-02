
> 查询SIM卡资费接口

####URL
<http://$AUTHSERVER/api/flow/month>

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
* 访问权限: ReadSIMDevice


####请求参数

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| access_token  | true    | string      | OAuth授权后获得。</br>注：通过HTTP认证头携带时省略。 |
| oid           | false   | string      | 机构标识 |
| limit         |   false |    int    |   分页参数，每页返回的最大条数。| 
| cursor         |  fasle |    int    |   分页参数，从第多少项开始查询。  |


####注意事项
无

####请求消息内容
``` JSON
{
"simId" : "1588888888",
    
"over" :1,  //1 全部  2超额
    
"time" : "201407",
    
"packageIds":[ "aaa","bb"…  ]

}
```

####返回结果
``` JSON
{
 "result":[
        {"simId":"13565558888",
        "deviceName":"Lamda",
        "useFlow":0.0,
        "packFlow":300.0,
        "basicMoney":30.0,
        "overMoney":0.0,
        "packName":"移动20套餐",
        "packId":"1406536697434199"}
 ],
 "total":500,
 "limit":10,
 "cursor":20
}
```
####返回值字段说明
| 返回值字段 | 字段类型 | 字段说明                |
| ---------- | --------:| :---------------------- |
| simId |   string | SIM卡号。 |
| deviceName |  String | 热点名。 |
| useFlow | double | 使用的流量。 |
| packFlow |  double | 对应套餐的流量。 |
| basicMoney  | double |  基本资费。 |
| overMoney  | double |  超额费用。 |
| packName  | String |  SIM卡对应套餐名。 |
| packId  | String |  套餐Id。 |
| total  | double |  SIM卡所使用的总费用。 |
####其他
无
