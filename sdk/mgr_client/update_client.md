# 更新用户组信息


## 修改配置
sdk使用之前需要先修改配置文件，参考[环境准备](/utoken/sdk/prerequisites)


**例：** 更新用户组信息：

1.  用户组ID： utoken-bibfag
2.  新用户组名： test2
3.  新业务组： test
4.  自定义描述： test2

## 请求示例

``` 
python utoken-tool.py  --cmd=update_client  \
                  --client_id=utoken-bibfag \
                  --client_name=test2       \
                  --business_group=test     \
                  --description=test2   
```

## 返回示例

    (200, {
            u'Message': u'ok', 
            u'RetCode': 0
          }
    )
