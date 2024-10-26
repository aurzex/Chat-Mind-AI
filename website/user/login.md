# 登录

> 登录 ChatMind AI 官网
> `/user/login` `POST` `200 OK`

## POST 请求参数

|   Key    |    Value    |  Type  |        |
| :------: | :---------: | :----: | :----: |
| phonenum | 手机号/邮箱 | string | `必须` |
| password |    密码     | string | `必须` |

## 返回内容

|  Key   |             Value              |  Type  |
| :----: | :----------------------------: | :----: |
|  code  |             响应码             |  int   |
| reason |            返回消息            | string |
|  data  | 返回数据 ([查看详情](#data)) |  JSON  |

### `data`

|       Key       |                    Value                    |  Type  |
| :-------------: | :-----------------------------------------: | :----: |
|    phonenum     |                   手机号                    | string |
|    username     |                    昵称                     | string |
|     avatar      |                  头像链接                   | string |
|      token      |                Authorization                | string |
|   inviteCode    |                   邀请码                    | string |
|   expireTime    |                   `未知`                    |  int   |
| checkDaysCount  |                   `未知`                    |  int   |
|   checkStatus   |                   `未知`                    |  bool  |
| lastUseModelsId |               上次使用角色 id               |  str   |
|    viplevel     |      VIP 等级([查看详情](#viplevel))      |  str   |
|   vipleftday    |                剩余 vip 天数                |  int   |
|     isread      |                   `未知`                    |  int   |
|   inBagModels   | 上一次聊天模型 ([查看详情](#inbagmodels)) |  JSON  |
|    ttsConfig    |  tts 语音设置 ([查看详情](#ttsconfig) )   |  JSON  |

#### `viplevel`

每个数字对应会员等级

| platform | Value  |
| :------: | :----: |
| 普通会员 | `未知` |
| 爱心会员 |   3    |
| 高级会员 | `未知` |
| 至臻会员 | `未知` |

#### `inBagModels`

|    Key    |                 Value                  |  Type  |
| :-------: | :------------------------------------: | :----: |
|  roleId   |                角色 id                 | string |
|  avatar   |                角色头像                | string |
|   name    |                角色名称                | string |
| modelName | 使用模型名称([查看详情](#modelname)) | string |

##### `modelName`

模型详情见`profile`

|    platform    |       Value       |
| :------------: | :---------------: |
|  MindGen 3.5   | gpt-3.5-turbo-16k |
|  MindGen 4.0   |      `未知`       |
|     Clara+     |      `未知`       |
|   文心大模型   |      `未知`       |
|     GLM-3      |      `未知`       |
|     GLM-4      |      `未知`       |
|  Clara3-Opus   |      `未知`       |
| Clara3-Sonnet  |      `未知`       |
| deepseek2 chat |      `未知`       |
|   qwen2 72b    |      `未知`       |
|  qwen1.5 110b  |      `未知`       |
|   qwen a14b    |      `未知`       |
| 混元 lite 256k |      `未知`       |

> 其余待补充

#### `ttsConfig`

|   Key    |  Value   |  Type  |
| :------: | :------: | :----: |
| language | 语音语言 | string |
|  voice   | 语音角色 | string |
|   name   |   语速   |  int   |
| language |   音调   |  int   |
|  voice   |   强度   |  int   |
|   name   | 语言情感 | string |

### 示例

```json
{
  "code": 200,
  "reason": "操作成功",
  "data": {
    "phonenum": "17393485788",
    "username": "猫鱼a",
    "token": "yourtoken",
    "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/04/06/1712373472484.jpg",
    "ttsConfig": {
      "language": "Chinese (普通话)",
      "voice": "zh-CN-XiaoxiaoNeural",
      "rate": 10,
      "range": 3,
      "styleDegree": 1.0,
      "style": "lyrical"
    },
    "inviteCode": "yourcode",
    "inBagModels": [
      {
        "roleId": "n4ixk1spyybuzeoyy311690646628538",
        "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/02/21/1708447932483.jpg",
        "name": "资深程序员v7.0 pre",
        "modelName": "gpt-3.5-turbo-16k"
      }
    ],
    "expireTime": -2,
    "checkDaysCount": 2,
    "checkStatus": true,
    "lastUseModelsId": "n4ixk1spyybuzeoyy311690646628538",
    "viplevel": "3",
    "vipleftday": 8,
    "isread": 1
  }
}
```
