# 获取用户排行榜 API 文档

> `api/market/userRank` `POST` `200 OK`

## 请求参数

| Key  | Value | Type | 是否必填 | 描述 |
| :--: | :---: | :--: | :------: | ---- |
| None |       |      |   必填   | 无   |

## 响应参数

|  Key   |                 Value                 |  Type  |          描述          |
| :----: | :-----------------------------------: | :----: | :--------------------: |
|  code  |                响应码                 |  int   |      200 表示成功      |
| reason |               返回消息                | string |  返回具体操作结果说明  |
|  data  | 用户排行榜信息数组([查看详情](#data)) |  JSON  | 包含多个用户的详细信息 |

### `data`

|  Key   |  Value   |  Type  |        描述        |
| :----: | :------: | :----: | :----------------: |
|   id   | 用户 ID  |  int   |  用户的唯一标识符  |
| avatar | 头像链接 | string | 用户的头像图片链接 |
|  heat  |   热度   |  int   |    用户的热度值    |
|  name  |  用户名  | string |     用户的名称     |

## 响应示例

```json
{
 "code": 200,
 "reason": "操作成功",
 "data": [
  {
   "id": 9,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/07/29/1690580492388.jpg",
   "heat": 100473266,
   "name": "超级无敌管理员🎈"
  },
  {
   "id": 13495,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/07/29/1690597011097.jpg",
   "heat": 22977376,
   "name": "Stell_A"
  },
  {
   "id": 129058,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/12/09/1702096992079.jpg",
   "heat": 20699948,
   "name": "QWERTY"
  },
  {
   "id": 52077,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/07/31/1722433763578.jpg",
   "heat": 19912446,
   "name": "猫鱼a"
  },
  {
   "id": 105662,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/07/29/1690589445713.jpg",
   "heat": 8927305,
   "name": "爱玩光遇和algodoo的李奕宸"
  },
  {
   "id": 144807,
   "avatar": "https://x.chatmindai.net/Logo.png",
   "heat": 6169090,
   "name": "某驾校校长【西璃版本】"
  },
  {
   "id": 65549,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/05/26/1716708597487.jpg",
   "heat": 4843954,
   "name": "惞"
  },
  {
   "id": 2678,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/01/26/1706282715863.jpg",
   "heat": 4047954,
   "name": "byk1"
  },
  {
   "id": 19064,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/08/14/1691973282883.jpg",
   "heat": 3060351,
   "name": "涡虫"
  },
  {
   "id": 1776,
   "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2023/08/12/1691855341276.jpg",
   "heat": 2965066,
   "name": "ikun"
  }
 ]
}
```
