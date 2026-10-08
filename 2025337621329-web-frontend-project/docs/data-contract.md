# data‑contract.md 数据契约与接口草案
学号：2025337621329
姓名：李一凡

> 全部为模拟虚构数据，无真实后端，使用Mock模拟接口。

## 1. 数据对象定义

### User 用户对象
|字段|类型|说明|来源|
|----|----|----|----|
|userId|string|用户id|前端mock|
|userName|string|用户姓名|前端mock|
|studentId|string|模拟学号|前端mock|

### Product 桶装水商品对象
|字段|类型|说明|来源|
|----|----|----|----|
|productId|string|商品编号|mock静态数据|
|name|string|水名称，例如“纯净水”“矿泉水”|mock静态数据|
|price|number|单价|mock静态数据|

### Order 订单对象
|字段|类型|说明|来源|
|----|----|----|----|
|orderId|string|订单编号|mock生成|
|userId|string|所属用户id|前端登录信息|
|productId|string|选购水商品id|表单选择|
|productName|string|商品名称|关联商品|
|building|string|楼栋|表单输入|
|roomNum|string|寝室号|表单输入|
|bucketCount|number|订购桶数|表单输入|
|remark|string|备注信息|表单输入，可为空|
|status|string|订单状态：pending待接单 / delivering配送中 / finished已送达|mock模拟流转|
|createTime|string|下单时间|前端生成时间字符串|

## 2. 接口草案

### 接口1：用户登录
- 名称：userLogin
- Method：POST
- URL：`/api/user/login`
- 请求参数
```json
{
  "studentId":"2025337621329",
  "password":"123456"
}
