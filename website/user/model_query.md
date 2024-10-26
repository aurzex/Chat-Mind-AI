# 获取推荐聊天模型列表 API

> `/api/model/query` `POST` `200 OK`

## 请求参数

|    Key    |                Value                | Type |                   描述                    |
| :-------: | :---------------------------------: | :--: | :---------------------------------------: |
| pageIndex |              当前页码               | int  | 表示从第几页开始获取数据，整数，从 1 开始 |
| pageSize  |             每页数据量              | int  |       决定返回的聊天模型数量，整数        |
|   data    | 筛选条件([查看详情](#request-data)) | JSON |            包含筛选条件的对象             |

### `request-data`

|     Key      |    Value     |  Type  |                    描述                     |
| :----------: | :----------: | :----: | :-----------------------------------------: |
| categoryName | 模型类别名称 | string |  值为`"recommend"`表示推荐模型，其他值待定  |
|  orderType   |   排序类型   | string | 值为`"recommend"`表示按推荐排序，其他值待定 |
| searchValue  |  搜索关键词  | string |            留空表示无筛选关键词             |

## 响应参数

|  Key   |                Value                 |  Type  |               描述               |
| :----: | :----------------------------------: | :----: | :------------------------------: |
|  code  |                响应码                |  int   |           200 表示成功           |
| reason |               返回消息               | string |       返回具体操作结果说明       |
|  data  | 数据对象([查看详情](#response-data)) |  JSON  | 包含模型列表及分页信息的详细内容 |

### `response-data`

|    Key    |    Value     | Type |                 描述                 |
| :-------: | :----------: | :--: | :----------------------------------: |
| pageIndex |   当前页码   | int  |             与请求中一致             |
| pageSize  |  每页数据量  | int  |             与请求中一致             |
|   total   |   总数据量   | int  |       当前筛选条件下的模型总数       |
|  hasNext  | 是否有下一页 | bool | 是否还有更多数据，`true`表示有下一页 |
|   data    | 模型信息数组 | JSON |      包含多个聊天模型的详细信息      |

### 模型详细字段说明 (`data` 数组中的每个对象)

|     Key      |        Value         |  Type  |                   描述                   |
| :----------: | :------------------: | :----: | :--------------------------------------: |
|    roleId    |       角色 ID        | string |            唯一标识模型的 ID             |
|    avatar    |       头像链接       | string |          模型对应的头像图片链接          |
|     name     |       角色名称       | string |                模型的名称                |
|   overview   |       模型概述       | string |           模型的特点、功能描述           |
|  modelName   |    使用的模型名称    | string |            模型的底层模型名称            |
|     tag      |         标签         | string |      该模型的标签（若无则为`null`）      |
|  updateDate  |       更新日期       | string |           该模型的最后更新日期           |
|  createDate  |       创建日期       | string |             该模型的创建日期             |
| isWebSearch  | 是否支持网络搜索功能 |  bool  |  是否支持联网搜索功能，`true`或`false`   |
| isMasterWork |  是否为主要工作模型  |  int   |          `1` 表示是，`0` 表示否          |
|  superRole   |    是否为超级角色    |  bool  |    是否具备超级权限，`true`或`false`     |
|   category   |       模型分类       | string | 模型所属类别，例如“学习办公”或“角色扮演” |
|    isHot     |       是否热门       |  int   |    `1` 表示是热门模型，`0` 表示非热门    |
|   hotcount   |       热度计数       |  int   |    热度值，表示该模型的使用或推荐次数    |

## 响应示例

```json
{
 "code": 200,
 "reason": "操作成功",
 "data": {
  "pageIndex": 1,
  "pageSize": 6,
  "total": 1655,
  "hasNext": true,
  "data": [
   {
    "roleId": "gd8u7ngfb4ye4gizxcl1726660048144",
    "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/09/18/1726660111391.jpg",
    "name": "MindGen o1-preview",
    "overview": "最新o1 模型，拥有「博士级」能力，快速解决复杂的科学、数学和编程问题。",
    "modelName": "o1-preview",
    "tag": null,
    "updateDate": "2024-10-26 22:17:14",
    "createDate": "2024-09-18 19:48:34",
    "isWebSearch": false,
    "isMasterWork": 0,
    "superRole": false,
    "category": "学习办公",
    "isHot": 1,
    "hotcount": 739725
   },
   {
    "roleId": "qr7l73qepjrblrda2ix1726660120123",
    "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/09/18/1726660141234.jpg",
    "name": "MindGen o1-mini",
    "overview": "表现几乎与o1 相当，o1-mini 是一种更快、更具成本效益的模型。",
    "modelName": "o1-mini",
    "tag": null,
    "updateDate": "2024-10-26 22:17:12",
    "createDate": "2024-09-18 19:49:07",
    "isWebSearch": false,
    "isMasterWork": 0,
    "superRole": false,
    "category": "角色扮演",
    "isHot": 1,
    "hotcount": 369641
   },
   {
    "roleId": "9axs5jp3936b1weaj741726510828189",
    "avatar": "https://x.chatmindai.net/api/uploads/reviewImage/2024/09/17/1726511230856.jpg",
    "name": "小玉兔 Otty",
    "overview": "嗨,我是小玉兔otty！（注意：参加活动请务必查看详细介绍里的链接）",
    "modelName": "ChatMindAi-4o-mini",
    "tag": null,
    "updateDate": "2024-10-26 22:17:12",
    "createDate": "2024-09-17 02:21:29",
    "isWebSearch": false,
    "isMasterWork": 0,
    "superRole": false,
    "category": "角色扮演",
    "isHot": 0,
    "hotcount": 65981
   }
  ]
 }
}
```
