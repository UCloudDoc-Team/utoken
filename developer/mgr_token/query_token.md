# 查看令牌

| URL  | <https://api.ucloud.cn?Action=GetUTokenList> |
| ---- | -------------------------------------------- |
| 请求方式 | POST                                         |
| 参数格式 | JSON                                         |

## 请求参数

| 字段名       | 类型     | 是否必选 | 描述                                                               |
| --------- | ------ | ---- | ---------------------------------------------------------------- |
| ClientID  | string | 是    | 用户组ID                                                            |
| ProjectId | int    | 是    | 项目ID                                                             |
| PublicKey | string | 是    | UCloud账号公钥                                                       |
| Signature | string | 是    | 签名，签名方式参考UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

## 返回结果

|           |        |                                                           |
| --------- | ------ | --------------------------------------------------------- |
| 字段名       | 类型     | 描述                                                        |
| RetCode   | int    | 错误码，参考 [](utoken/developer/errorcode) |
| Message   | string | 错误信息                                                      |
| Timestamp | int    | 结果返回时间(unix时间戳)                                           |
| Result    | array  | 查询结果列表                                                    |

## 单个查询结果（格式：object）

| 字段名          | 类型     | 描述                     |
| ------------ | ------ | ---------------------- |
| TokenID      | int    | 令牌ID                   |
| TokenName    | string | 令牌名称                   |
| Token        | string | 令牌(32位字符串)             |
| TopOrgID     | int    | 组织ID                   |
| ProjectID    | int    | 项目ID                   |
| BeginTime    | int    | 令牌有效期始（unix时间戳）        |
| EndTime      | int    | 令牌有效期止（unix时间戳）        |
| Period       | int    | 令牌更新周期（单位：秒）           |
| UpdateMethod | int    | 令牌更新方式，1: 到期失效； 2：自动续期 |

**注**：查询结果中的Token被隐藏，为 \*。第一次创建token时须记住。

## 请求示例

``` 
curl -X POST https://api.ucloud.cn/?Action=GetUTokenList -d '
{
  “Action”:"GetUTokenList",
  "ClientID":"1",
  "ProjectId":7,
  "PublicKey": "xxx",
  "Signature": "xxx"
}

```

## 返回示例

    {
      "RetCode": 0,
      "Message": "PJGUYoct",
      "Timestamp": 6,
      "Result": [
        {
          "TokenID": 1,
          “Token”: "*",
          "TopOrgID": 12,
          "ProjectID": 13,
          "BeginTime": 123,
          "EndTime": 1234,
          "Period": 600,
          "UpdateMethod": 2
        }
      ]
    }
