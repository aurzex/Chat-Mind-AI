# 获取 API 调用配额信息 API 文档

> `api/apiCount/query` `GET` `200 OK`

## 响应参数

|  Key   |    Value     |  Type  |             描述             |
| :----: | :----------: | :----: | :--------------------------: |
|  code  |    响应码    |  int   |         200 表示成功         |
| reason |   返回消息   | string |     返回具体操作结果说明     |
|  data  | 配额详情对象 |  JSON  | 包含不同类别的配额和剩余次数 |

### `data`

|        Key        |      Value       | Type |            描述            |
| :---------------: | :--------------: | :--: | :------------------------: |
| basicRemainCount  | 基础模型剩余次数 | int  | 表示基础模型的剩余调用次数 |
| seniorRemainCount | 高级模型剩余次数 | int  | 表示高级模型的剩余调用次数 |
|    basicLimit     | 基础模型调用上限 | int  |   基础模型的每日调用上限   |
|    seniorLimit    | 高级模型调用上限 | int  |   高级模型的每日调用上限   |
| limitRemainCount  | 限制模型剩余次数 | int  |   限制模型的剩余调用次数   |
|    limitLimit     | 限制模型调用上限 | int  |   限制模型的每日调用上限   |

## 响应示例

```json
{
 "code": 200,
 "reason": "操作成功",
 "data": {
  "basicRemainCount": 237,
  "seniorRemainCount": 13,
  "basicLimit": 240,
  "seniorLimit": 120,
  "limitRemainCount": 20,
  "limitLimit": 20
 }
}
```
