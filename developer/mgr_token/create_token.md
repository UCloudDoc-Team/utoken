{{indexmenu_n>1}}

\======== 创建令牌 ========

| URL  | <https://api.ucloud.cn?Action=CreateUTokenToken> |
| ---- | ------------------------------------------------ |
| 请求方式 | POST                                             |
| 参数格式 | JSON                                             |

\*\* 请求参数： \*\*

| 字段名          | 类型     | 是否必选 | 描述                                                              |
| ------------ | ------ | ---- | --------------------------------------------------------------- |
| ClientID     | string | 是    | 用户组ID                                                           |
| TokenName    | string | 是    | 令牌名（可重复，256字符以内）                                                |
| UpdateMethod | int    | 是    | 续期方式，1: 到期失效； 2: 自动续期                                           |
| Period       | int    | 是    | 令牌更新周期（单位:秒）支持的周期有：5、10、15、20、30分钟，1、2、6, 12, 24小时              |
| ProjectId    | int    | 是    | 项目ID                                                            |
| Action       | string | 是    | 固定值：CreateUTokenToken                                           |
| PublicKey    | string | 是    | UCloud账号公钥                                                      |
| Signature    | string | 是    | 签名，生成方式见UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

\*\* 返回结果： \*\*

| 字段名       | 类型     | 描述                                                        |
| --------- | ------ | --------------------------------------------------------- |
| RetCode   | int    | 错误码，参考 [](/management_monitor/utoken/developer/errorcode) |
| Message   | string | 错误信息                                                      |
| Timestamp | int    | 结果返回时间(unix时间戳)                                           |
| TokenID   | int    | 令牌ID                                                      |
| Token     | string | 令牌(32位字符串)                                                |
| BeginTime | int    | 令牌有效期始(unix时间戳)                                           |
| EndTime   | int    | 令牌有效期止(unix时间戳)                                           |

\*\* \*注：令牌查询结果中的Token被隐藏为 \*。第一次创建token时须记住。 \*\*

\*\* 请求示例 \*\*

``` 
curl -X POST https://api.ucloud.cn/?Action=CreateUTokenToken -d '
{
  "Action": "CreateUTokenToken",
  "ClientID":"3",
  "ProjectId":1,
  "TokenName":"pbbGEZsJ",
  "UpdateMethod": 1,
  "Period": 600,
  "PublicKey": "xxxx",
  "Signature": "xxxx"
}

```

\*\* 返回示例 \*\*

    {
      "RetCode": 0,
      "Message": "OoTaaldZ",
      "TokenID": 1,
      "Token": "tFkKlVkm",
      "BeginTime": 1,
      "EndTime": 1,
      "Timestamp": 3
    }
