

\======= 创建用户组 ======

| URL  | <https://api.ucloud.cn?Action=CreateUTokenClient> |
| ---- | ------------------------------------------------- |
| 请求方式 | POST                                              |
| 参数格式 | JSON                                              |

\*\* 请求参数 \*\*

| 字段名           | 类型     | 是否必选 | 描述                                                               |
| ------------- | ------ | ---- | ---------------------------------------------------------------- |
| ProjectId     | int    | 是    | 项目ID                                                             |
| BusinessGroup | string | 是    | 业务组                                                              |
| ClientName    | string | 是    | 用户组名（长度小于256字符）                                                  |
| Description   | string | 否    | 自定义描述字段（长度小于256字符）                                               |
| PublicKey     | string | 是    | UCloud账号公钥                                                       |
| Signature     | string | 是    | 签名，生成方式参考UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

\*\* 返回结果 \*\*

| 字段名        | 类型     | 描述                                                        |
| ---------- | ------ | --------------------------------------------------------- |
| RetCode    | int    | 错误码，参考 [](/management_monitor/utoken/developer/errorcode) |
| Message    | string | 错误信息                                                      |
| Timestamp  | int    | 结果返回时间（unix时间戳）                                           |
| ClientID   | string | 用户组ID                                                     |
| CreateTime | int    | 用户组创建时间（unix时间戳）                                          |

\*\* 请求示例 \*\*

    curl -X POST https://api.ucloud.cn/?Action=CreateUTokenClient -d '
    {
      "Action": "CreateUTokenClient",
      "ProjectId" : 2,
      "ClientName" : "YrGMyecy",
      "Description" : "inbgEvaU",
      "BusinessGroup": "test",
      "PublicKey": "xxxx",
      "Signature": "xxxx"
    }'

\*\* 返回示例 \*\*

    {
      "RetCode": 0,
      "Message": "bUWplQYc",
      "ClientID": 7,
      "CreateTime": 9,
      "Timestamp": 5
    }
