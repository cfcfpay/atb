# 交易查询接口

> ## 接口地址

请求方式：`HTTP POST`

    https://pay.bfpay.cc/query_order/

>## 请求参数

参数名称|含义|类型|必填/选填|说明
:--:|:--:|:--:|:--:|:--:
uid|用户UID|string|必填|您的唯一标识，注册后在“基本配置”页面里获得，一个32位字符串。
order_no|商户订单|double/float|必填|在回调里获取的的商户订单号。

>## 响应参数

参数名称|含义|类型|说明
:--:|:--:|:--:|:--:
msg|请求状态描述|string|"用于扫描状态码的说明信息，如：“查询成功”、“uid和auth_code 无法通过验证 请检查这两参数配置是否正确”"
code|返回状态码|string|状态码，用于标记接口的请求状态,200代表成功，其他代码表示请求失败，失败原因看msg字段
total_amount|金额|double/float|用户实际支付的金额
money|金额|double/float|用户提交的金额
channel|支付类型|string|支付平台，支付宝或者微信 ALIPAY wechat 这两个值，当前仅会返回ALIPAY
order_no|商户编号|string|后台返回的商户编号
order_id|订单编号|string|您在发起付款接口里传入的订单号
pay_status|支付状态|string|"支付状态，PAYING:支付中,TRADE_SUCCESS:已支付,TRADE_CLOSE:支付关闭"
add_time|创建时间|string|订单创建的时间
pay_time|支付时间|string|订单支付的时间
user_msg|备注|string|

>## 响应示例JSON

```json
{
    "msg": "查询成功",
    "code": 200,
    "total_amount": 1,
    "money"："1",
    "usr_msg": "测试20190319",
    "add_time": "2019-03-20T17:11:04",
    "pay_status": "TRADE_SUCCESS",
    "order_no": "20190320171103327296265",
    "order_id": "201902231113111111",
    "pay_time": "2019-03-20T17:11:13.113310",
    "channel":"atb"
}
```






