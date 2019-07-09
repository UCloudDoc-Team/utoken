{{indexmenu_n>30}}

\======= 查看用户组 ========

| URL  | <https://api.ucloud.cn?Action=GetUTokenClient> |
| ---- | ---------------------------------------------- |
| 请求方式 | POST                                           |
| 参数格式 | JSON                                           |

\*\* 请求参数 \*\*

| 字段名       | 类型     | 是否必选 | 描述                                                               |
| --------- | ------ | ---- | ---------------------------------------------------------------- |
| ProjectId | int    | 是    | 项目ID                                                             |
| PublicKey | string | 是    | UCloud账号公钥                                                       |
| Signature | string | 是    | 签名，生成方式参考UCloud文档 <https://docs.ucloud.cn/api/summary/signature> |

\*\* 返回结果 \*\*

| 字段名       | 类型     | 描述                                                        |
| --------- | ------ | --------------------------------------------------------- |
| RetCode   | int    | 错误码，参考 [](/management_monitor/utoken/developer/errorcode) |
| Message   | string | 错误信息                                                      |
| Timestamp | int    | 结果返回时间（unix时间戳）                                           |
| Result    | array  | 查询结果列表                                                    |

\*\* 单个查询结果（类型：object） \*\*

| 字段名           | 类型     | 描述                   |
| ------------- | ------ | -------------------- |
| ClientID      | string | 用户组ID                |
| ClientName    | string | 用户组名                 |
| BusinessGroup | string | 业务组名                 |
| Description   | string | 用户自定义描述              |
| Quota         | int    | 配额，业务组可同时拥有的有效令牌最大个数 |
| TokenNum      | int    | 用户组当前有效令牌个数          |
| CreateTime    | int    | 用户组创建时间              |
| ModifyTime    | int    | 用户组信息最后修改时间          |

\*\* 请求示例 \*\*

``` 
curl -X POST https://api.ucloud.cn/?Action=GetUTokenClient -d '
{
  "ProjectId": 9,
  "PublicKey": "xxxx",
  "Signature": "xxxx"
}

```

\*\* 返回示例 \*\*

    {
      "RetCode": 0,
      "Message": "UIgwBnde",
      "Timestamp": 4,
      "Result": [
        {
          "ClientID": 123,
          "ClientName": "test",
          "BusinessGroup": "xxx",
          "CreateTime": 1534843416,
          "ModifyTime": 1534843416,
          "Description": "test",
          "Quota": 10,
          "TokenNum": 1
        }
      ],
    }
