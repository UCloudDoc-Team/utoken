

\========= 更新令牌续期方式 ==========

| URL  | <https://api.ucloud.cn?Action=UpdateUTokenToken> |
| ---- | ------------------------------------------------ |
| 请求方式 | POST                                             |
| 参数格式 | JSON                                             |

\*\* 请求参数 \*\*

| 字段名          | 类型     | 是否必选 | 描述                                                               |
| ------------ | ------ | ---- | ---------------------------------------------------------------- |
| ClientID     | string | 是    | 用户组ID                                                            |
| UpdateMethod | int    | 是    | 令牌续期方式(只能由2修改为1), 1: 到期失效； 2: 自动续期                               |
| ProjectId    | int    | 是    | 项目ID                                                             |
| TokenID      | int    | 是    | 令牌ID                                                             |
| PublicKey    | string | 是    | UCloud账号公钥                                                       |
| Signature    | string | 是    | 签名，签名方式参考UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

\*\* 返回结果 \*\*

| 字段名       | 类型     | 描述                                                        |
| --------- | ------ | --------------------------------------------------------- |
| RetCode   | int    | 错误码，参考 [](utoken/developer/errorcode) |
| Message   | string | 错误信息                                                      |
| Timestamp | int    | 结果返回时间(unix时间戳)                                           |

\*\* 请求示例 \*\*

``` 
curl -X POST https://api.ucloud.cn/?Action=UpdateUTokenToken -d '
{
  "Action": "UpdateUTokenToken",
  "ClientID":"9",
  "UpdateMethod":1,
  "ProjectId":1,
  "TokenID": 2,
  "PublicKey": "xxxx",
  "Signature": "xxxx"
}'

```

\*\* 返回示例 \*\*

    {
      "RetCode": 0,
      "Message": "tOlUuPuJ",
      "Timestamp": 7
    }
