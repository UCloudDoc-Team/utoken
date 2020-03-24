

# 创建令牌

\*\* sdk使用之前需要先修改配置文件，参考[](utoken/sdk/prerequisites)
\*\*

**例：** 创建令牌：

1.  用户组ID： utoken-bibfag
2.  令牌名： token1
3.  续期方式： 自动续期
4.  有效时间： 10分钟

\*\* 请求示例 \*\*

    python utoken-tool.py  --cmd=create_token       \
                          --client_id=utoken-bibfag \
                          --token_name=token1       \
                          --update_method=2         \
                          --period=600

\*\* 返回示例 \*\*

    (200, {
            u'RetCode': 0, 
            u'TokenID': 151, 
            u'Token': u'fe2ba83b056e0d38444b922239c9443e', 
            u'BeginTime': 1538293352, 
            u'Message': u'ok', 
            u'EndTime': 1538293952
          }
    )
