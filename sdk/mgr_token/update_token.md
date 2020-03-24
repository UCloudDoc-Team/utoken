

## 更新令牌续期方式

\*\* sdk使用之前需要先修改配置文件，参考[](utoken/sdk/prerequisites)
\*\*

**例：** 更新令牌续期方式：

1.  令牌ID： 151
2.  用户组ID： utoken-bibfag
3.  续期方式： 到期失效

\*\* 请求示例 \*\*

    python utoken-tool.py  --cmd=update_token       \
                          --client_id=utoken-bibfag \
                          --token_id=151            \
                          --update_method=1

\*\* 返回示例 \*\*

    (200, {
            u'Message': u'ok', 
            u'RetCode': 0
          }
    )
