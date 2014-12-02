
> 更改SIM卡套餐绑定关系

####URL
<http://$AUTHSERVER/api/flow/changesimpack>

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
* 访问权限: WriteSIMPack


####请求参数

| 请求参数      |    必选 | 类型及范围  | 说明                                |
| ------------- | -------:| :---------- | ----------------------------------- |
| access_token  | true    | string      | OAuth授权后获得。</br>注：通过HTTP认证头携带时省略。 |
| oid           | false   | string      | 机构标识 |

####注意事项
无

####请求消息内容
``` JSON
{
"simId" : "12",  
    
"packageId" : "123.."  //套餐Id

}

```

####返回结果
``` JSON
{
 "result": "success"
}
```
####返回值字段说明

####其他
无
