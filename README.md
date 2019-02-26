# wxapi - 微信小程序开发接口工具包

微信小程序接口工具包，无需服务器，无需开发后台，开箱即用，轻松开发小程序

交流 QQ 群: 629639122

欢迎大家进群交流，文档持续更新中...

## 使用方法

1. 将本项目文件夹 "wxapi" 复制到您的小程序根目录；

2. 修改 config.js 文件， subDomain 改为你自己的域名

   > 你可以 [免费开通后台账号](https://www.it120.cc/) ，开通后查看您的 subDomain 「[如何查看专属 subDomain](https://www.it120.cc/info/faq/10468)」

3. 登录你的[小程序后台](https://mp.weixin.qq.com)，[设置小程序合法服务器域名](https://www.it120.cc/info/faq/10469)，修改后需要重启小程序开发工具才能生效

4. 在您需要的地方引用工具类

   > const WXAPI = require('wxapi/main')
   >
   > 或者
   >
   > import WXAPI from 'wxapi/main'

5. 根据下面的文档调用接口即可

## 调用示例

> 调用：

```java
WXAPI.queryMobileLocation({ mobile: '13500000000' }).then(res => {
    console.log('接口成功返回:', res)
}).catch(e => {
    console.error('接口调用异常:', e)
})
```

> 返回：

```java
{
  "code": 0,
  "data": {
    "areaCode": "020",
    "cardType": "GSM",
    "cityName": "广州",
    "code": 1350000,
    "id": 60113,
    "postCode": "510000",
    "province": "广东",
    "segmentName": "中国移动"
  },
  "msg": "success"
}
```

## 参数说明

接口参数说明: [「查看接口文档」](https://api.it120.cc/doc.html)

## 接口文档

<!-- TOC -->autoauto- [wxapi - 微信小程序开发接口工具包](#wxapi---微信小程序开发接口工具包)auto  - [使用方法](#使用方法)auto  - [调用示例](#调用示例)auto  - [参数说明](#参数说明)auto  - [接口文档](#接口文档)auto    - [登录 & 注册](#登录--注册)auto      - [用户注册](#用户注册)auto      - [用户登录](#用户登录)auto      - [检测登录 token 是否有效](#检测登录-token-是否有效)auto    - [用户信息](#用户信息)auto      - [绑定手机号码](#绑定手机号码)auto      - [获取用户信息](#获取用户信息)auto      - [获取用户资产（余额、可用积分）信息](#获取用户资产余额可用积分信息)auto      - [用户资金流水](#用户资金流水)auto      - [申请提现](#申请提现)auto    - [基础数据检索](#基础数据检索)auto      - [读取所有省份](#读取所有省份)auto      - [读取下级省市区数据](#读取下级省市区数据)auto      - [查询手机号码归属地](#查询手机号码归属地)auto    - [读取 Banner 列表](#读取-banner-列表)auto    - [商品管理](#商品管理)auto      - [获取所有的商品分类](#获取所有的商品分类)auto      - [获取商品列表](#获取商品列表)auto      - [获取商品详情信息](#获取商品详情信息)auto      - [获取商品价格（一般用户选择了不同规格尺寸后读取新价格）](#获取商品价格一般用户选择了不同规格尺寸后读取新价格)auto      - [获取商品的评价](#获取商品的评价)auto    - [读取后台设置的系统参数](#读取后台设置的系统参数)auto    - [根据视频编号读取视频详情](#根据视频编号读取视频详情)auto    - [优惠券管理](#优惠券管理)auto      - [获取可领取优惠券](#获取可领取优惠券)auto      - [领取优惠券](#领取优惠券)auto      - [获取我的优惠券](#获取我的优惠券)auto    - [公告管理](#公告管理)auto      - [获取公告列表](#获取公告列表)auto      - [获取公告详情](#获取公告详情)auto    - [订单管理](#订单管理)auto      - [我的订单统计](#我的订单统计)auto      - [创建订单](#创建订单)auto      - [查询订单列表](#查询订单列表)auto      - [查询订单详情](#查询订单详情)auto      - [确认收货接口](#确认收货接口)auto      - [评价接口](#评价接口)auto      - [关闭订单](#关闭订单)auto      - [使用余额支付订单](#使用余额支付订单)auto    - [积分管理](#积分管理)auto      - [读取积分赠送规则](#读取积分赠送规则)auto      - [签到](#签到)auto      - [签到记录](#签到记录)auto      - [读取今日签到信息](#读取今日签到信息)auto      - [使用积分券兑换积分](#使用积分券兑换积分)auto      - [积分明细记录](#积分明细记录)auto    - [模板消息](#模板消息)auto      - [记录 formid/预支付 id 用以后期发送消息](#记录-formid预支付-id-用以后期发送消息)auto      - [给用户发送模板消息](#给用户发送模板消息)auto    - [收货地址管理](#收货地址管理)auto      - [获取收货地址列表](#获取收货地址列表)auto      - [添加收货地址](#添加收货地址)auto      - [更新收货地址](#更新收货地址)auto      - [获取默认地址](#获取默认地址)auto      - [读取地址详细信息](#读取地址详细信息)auto      - [删除](#删除)auto    - [在线支付](#在线支付)auto      - [微信支付](#微信支付)auto      - [支付宝支付(半自动)](#支付宝支付半自动)auto    - [商品砍价](#商品砍价)auto      - [获取可砍价的商品列表](#获取可砍价的商品列表)auto      - [发起一个砍价](#发起一个砍价)auto      - [砍价详情](#砍价详情)auto      - [砍价助力](#砍价助力)auto      - [我的助力信息](#我的助力信息)auto    - [拼团功能](#拼团功能)auto      - [开团接口](#开团接口)auto      - [获取某个商品当前进行中的所有拼团](#获取某个商品当前进行中的所有拼团)auto    - [资金相关](#资金相关)auto      - [获取充值满多少送多少规则](#获取充值满多少送多少规则)autoauto<!-- /TOC -->

### 登录 & 注册

#### 用户注册

> WXAPI.register(Object object)

#### 用户登录

> WXAPI.login(Object object)

#### 检测登录 token 是否有效

> WXAPI.checkToken(token)

### 用户信息

#### 绑定手机号码

> WXAPI.bindMobile(Object object)

#### 获取用户信息

> WXAPI.userDetail(token)

#### 获取用户资产（余额、可用积分）信息

> WXAPI.userAmount(token)

#### 用户资金流水

> WXAPI.cashLogs(Object object)

#### 申请提现

> WXAPI.withDrawApply(money, token)

### 基础数据检索

#### 读取所有省份

> WXAPI.province()

#### 读取下级省市区数据

> WXAPI.nextRegion(pid)

#### 查询手机号码归属地

> WXAPI.queryMobileLocation(Object object)

### 读取 Banner 列表

> WXAPI.banners(Object object)

### 商品管理

#### 获取所有的商品分类

> WXAPI.goodsCategory()

#### 获取商品列表

> WXAPI.goods(Object object)

#### 获取商品详情信息

> WXAPI.goodsDetail(id)

#### 获取商品价格（一般用户选择了不同规格尺寸后读取新价格）

> WXAPI.goodsPrice(Object object)

#### 获取商品的评价

> WXAPI.goodsReputation(Object object)

### 读取后台设置的系统参数

> WXAPI.queryConfig(Object object)

### 根据视频编号读取视频详情

> WXAPI.videoDetail(videoId)

### 优惠券管理

#### 获取可领取优惠券

> WXAPI.coupons(Object object)

#### 领取优惠券

> WXAPI.fetchCoupons(Object object)

#### 获取我的优惠券

> WXAPI.myCoupons(Object object)

### 公告管理

#### 获取公告列表

> WXAPI.noticeList(Object object)

#### 获取公告详情

> WXAPI.noticeDetail(id)

### 订单管理

#### 我的订单统计

> WXAPI.orderStatistics(token)

#### 创建订单

> WXAPI.orderCreate(Object object)

#### 查询订单列表

> WXAPI.orderList(Object object)

#### 查询订单详情

> WXAPI.orderDetail(id, token)

#### 确认收货接口

> WXAPI.orderDelivery(orderId, token)

#### 评价接口

> WXAPI.orderReputation(Object object)

#### 关闭订单

> WXAPI.orderClose(orderId, token)

#### 使用余额支付订单

> WXAPI.orderPay(orderId, token)

### 积分管理

#### 读取积分赠送规则

> WXAPI.scoreRules(Object object)

#### 签到

> WXAPI.scoreSign(token)

#### 签到记录

> WXAPI.scoreSignLogs(Object object)

#### 读取今日签到信息

> WXAPI.scoreTodaySignedInfo(token)

#### 使用积分券兑换积分

> WXAPI.scoreExchange(number, token)

#### 积分明细记录

> WXAPI.scoreLogs(Object object)

### 模板消息

#### 记录 formid/预支付 id 用以后期发送消息

> WXAPI.addTempleMsgFormid(Object object)

#### 给用户发送模板消息

> WXAPI.sendTempleMsg(Object object)

### 收货地址管理

#### 获取收货地址列表

> WXAPI.queryAddress(token)

#### 添加收货地址

> WXAPI.addAddress(Object object)

#### 更新收货地址

> WXAPI.updateAddress(Object object)

#### 获取默认地址

> WXAPI.defaultAddress(token)

#### 读取地址详细信息

> WXAPI.addressDetail(id, token)

#### 删除

> WXAPI.deleteAddress(id, token)

### 在线支付

#### 微信支付

> WXAPI.wxpay(Object object)

#### 支付宝支付(半自动)

> WXAPI.alipay(Object object)

### 商品砍价

#### 获取可砍价的商品列表

> WXAPI.kanjiaList(Object object)

#### 发起一个砍价

> WXAPI.kanjiaJoin(kjid, token)

#### 砍价详情

> WXAPI.kanjiaDetail(kjid, joiner)

#### 砍价助力

> WXAPI.kanjiaHelp(kjid, joiner, token, remark)

#### 我的助力信息

> WXAPI.kanjiaHelpDetail(kjid, joiner, token)

### 拼团功能

#### 开团接口

> WXAPI.pingtuanOpen(goodsId, token)

#### 获取某个商品当前进行中的所有拼团

> WXAPI.pingtuanList(goodsId)

### 资金相关

#### 获取充值满多少送多少规则

> WXAPI.rechargeSendRules()
