

# 查看用户组

\*\* sdk使用之前需要先修改配置文件，参考[](utoken/sdk/prerequisites)
\*\*

**例：** 查看用户组：

1.  用户组ID： utoken-bibfag

\*\* 请求示例 \*\*

``` 
python utoken-tool.py  --cmd=get_client      \
                        --client_id=utoken-bibfag      
```

\*\* 返回示例 \*\*

    (200, {
            u'Timestamp': 1538292857, 
            u'Message': u'ok', 
            u'Result': [
              {
                u'Description': u'test2', 
                u'Quota': 10, 
                u'ClientID': u'utoken-bibfag', 
                u'BusinessGroup': u'test', 
                u'ModifyTime': 1538321557, 
                u'TokenNum': 0, 
                u'CreateTime': 1538321397, 
                u'ClientName': u'test2'
              }], 
            u'RetCode': 0
          }
      )
