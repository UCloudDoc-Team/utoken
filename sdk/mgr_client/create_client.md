{{indexmenu_n>1}}

# 创建用户组

\*\* sdk使用之前需要先修改配置文件，参考[](/management_monitor/utoken/sdk/prerequisites)
\*\*

**例：** 创建用户组：

1.  用户组名： test
2.  业务组： default
3.  自定义描述： test

\*\* 请求示例 \*\*

``` 
python utoken-tool.py  --cmd=create_client \
                  --client_name=test       \
                  --business_group=default \
                  --description=test   
```

\*\* 返回示例 \*\*

    (200, {
            u'Message': u'ok', 
            u'CreateTime': 1538321139, 
            u'ClientID': u'utoken-nlc0zj', 
            u'RetCode': 0
          }
    )
