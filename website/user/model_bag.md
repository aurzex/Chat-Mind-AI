# 获取聊天模型列表 API 文档

> `/api/user/queryInBagModels` `GET` `200 OK`

## 响应参数

|  Key   |                Value                |  Type  |            描述            |
| :----: | :---------------------------------: | :----: | :------------------------: |
|  code  |               响应码                |  int   |        200 表示成功        |
| reason |              返回消息               | string |    返回具体操作结果说明    |
|  data  | 聊天模型信息数组([查看详情](#data)) |  JSON  | 包含多个聊天模型的详细信息 |

### `data`

每个聊天模型的详细信息包含以下字段：

|       Key       |     Value      |  Type  |                 描述                 |
| :-------------: | :------------: | :----: | :----------------------------------: |
|     roleId      |    角色 ID     | string |          唯一标识模型的 ID           |
|     avatar      |    头像链接    | string |        模型对应的头像图片链接        |
|      name       |    角色名称    | string |              模型的名称              |
|    modelName    | 使用的模型名称 | string |          模型的底层模型名称          |
|    overview     |    模型概述    | string |         模型的特点、功能描述         |
| patternCategory |    模型类别    | string | 可能的值：`basic`、`senior`、`limit` |

## 响应示例

```json
{
 "code": 200,
 "reason": "操作成功",
 "data": [
  {
   "roleId": "8kfs3y3ldlfbg436sld1699515414980",
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/11/09/1699515423675.jpg",
   "name": "万能助手 4.0",
   "modelName": "ChatMindAi-4-all",
   "overview": "4.0模型的最新版本，“识图”、”绘图“、”分析“，“联网搜索”，全部all in one！！",
   "patternCategory": "senior"
  },
  {
   "roleId": "djt4qce8ywpaxtb6k6y1721874024447",
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/07/25/1721874089756.jpg",
   "name": "Clara3.5-Sonnet",
   "modelName": "Clara-35-sonnet",
   "overview": "Clara系列最先进的版本！",
   "patternCategory": "senior"
  }
 ]
}
```
