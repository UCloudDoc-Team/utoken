# 更新用户组信息

| URL  | <https://api.ucloud.cn?Action=UpdateUTokenClient> |
| ---- | ------------------------------------------------- |
| 请求方式 | POST                                              |
| 参数格式 | JSON                                              |

## 请求参数

| 字段名           | 类型     | 是否必选 | 描述                                                               |
| ------------- | ------ | ---- | ---------------------------------------------------------------- |
| ClientID      | string | 是    | 业务组ID                                                            |
| ProjectId     | int    | 是    | 项目ID                                                             |
| ClientName    | string | 否    | 用户组名                                                             |
| BusinessGroup | string | 否    | 业务组名                                                             |
| Description   | string | 否    | 用户自定义描述（长度不超过256字符）                                              |
| PublicKey     | string | 是    | UCloud账号公钥                                                       |
| Signature     | string | 是    | 签名，生成方式参考UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

**注**：ClientName, BusinessGroup, Description至少有一个更新

## 返回结果

| 字段名       | 类型     | 描述                                                         |
| --------- | ------ | ---------------------------------------------------------- |
| RetCode   | int    | 错误码， 参考 [](/management_monitor/utoken/developer/errorcode) |
| Message   | string | 错误信息                                                       |
| Timestamp | int    | 结果返回时间（unix时间戳）                                            |

## 请求示例

    curl -X POST https://api.ucloud.cn/?Action=UpdateUTokenClient -d '
    {
      "Action": "UpdateUTokenClient",
      "ClientID":“8”,
      "ProjectId":7,
      "ClientName":"hSaeSlen",
      "BusinessGroup":"test",
      "Description": "KcRcfcCX",
      "PublicKey": "xxxxx",
      "Signature": "xxxxx"
    }'

## 返回示例

    {
      "RetCode": 0,
      "Message": "fiKxDAar",
      "Timestamp": "eYyIxgEu"
    }
