

\======== 环境准备 ========

**SDK运行环境**

\- **Python2.7** - **requests** (若安装anaconda2环境，则无需安装)

    pip install requests

\- **utoken-sdk**

    git clone https://github.com/ucloud/utoken-sdk.git

**配置账号信息**

修改utoken-sdk中配置文件config.json(配置文件中不能包含注释)

    {
      "public_key": "xxxxxxxx",
      "private_key": "xxxxxxx",
      "region": "xxxxx",
      "zone": "xxxxxx",
      "project_id": xxxxxx,
    }
