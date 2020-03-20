# 删除用户组

## 修改配置
sdk使用之前需要先修改配置文件，参考[环境准备](/management_monitor/utoken/sdk/prerequisites)

**例：** 删除用户组：

1.  用户组ID： utoken-nlc0zj

## 请求示例

    python utoken-tool.py  --cmd=delete_client      \
                      --client_id=utoken-nlc0zj

## 返回示例

    (200, {
            u'Message': u'ok', 
            u'RetCode': 0
          }
    )
