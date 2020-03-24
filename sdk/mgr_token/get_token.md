

# 查看令牌

\*\* sdk使用之前需要先修改配置文件，参考[](utoken/sdk/prerequisites)
\*\*

**例：** 查看令牌：

1.  用户组ID： utoken-bibfag

\*\* 请求示例 \*\*

    python utoken-tool.py  --cmd=get_token      \
                          --client_id=utoken-bibfag

\*\* 返回示例 \*\*

    (200, {
            u'Timestamp': 1538293711, 
            u'Message': u'ok', 
            u'Result': [
              {
                u'TopOrgID': 200000510, 
                u'TokenID': 151, 
                u'ProjectID': 200000860, 
                u'TokenName': u'token1', 
                u'Period': 600, 
                u'UpdateMethod': 1, 
                u'Token': u'*', 
                u'BeginTime': 1538293352, 
                u'EndTime': 1538294211
              }
            ], 
            u'RetCode': 0
          }
    )
