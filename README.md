# 瑞幸咖啡 MCP（luckin-coffee）

把瑞幸点单能力接进 Operit，用自然语言完成：查附近门店 → 搜商品 → 选规格 → 看详情 → 预览价格 → 下单取餐。

> ⚠️ 本仓不含任何 Token / 凭据。Token 由品牌官方渠道发放，各人自有，请自行获取。

## 一、需要什么

| 项 | 说明 |
|---|---|
| MCP 类型 | remote（远程） |
| 接入方式 | streamablehttp |
| 端点 | `https://gwmcp.lkcoffee.com/order/user/mcp` |
| 认证方式 | 请求头 `Authorization: Bearer <你的 Token>` |
| Token 从哪来 | 到 open.lkcoffee.com 登录后复制，各人自有，本仓不提供 |
| 附加说明 | 端点域名 / 路径以品牌官方最新文档为准 |

## 二、在 Operit 里怎么装

1. 打开 Operit → MCP 插件配置
2. 新增一个 **远程 MCP**
3. 填：

```
名称：瑞幸咖啡 MCP
地址：https://gwmcp.lkcoffee.com/order/user/mcp
类型：httpStream（streamablehttp）
Bearer Token：<你自己的 Token>
```

4. 保存 → 拉取工具列表，装成功即可在对话里直接用。

也可以直接导入 `mcp_config.example.json`，把里面的 `<YOUR_LUCKIN_TOKEN>` 换成自己的 Token。

## 三、能做什么（8 个工具）

| 工具 | 用途 |
|---|---|
| `queryShopList` | 按门店名 / 经纬度查附近门店 |
| `searchProductForMcp` | 按自然语言关键词搜商品 |
| `switchProduct` | 切换商品规格（冰热 / 糖度 / 浓度 / 杯型 / 小料） |
| `queryProductDetailInfo` | 查单个商品详情 |
| `previewOrder` | 订单预览，纯算价，不生成订单、不扣钱 |
| `createOrder` | 创建订单，返回支付链接 / 二维码 |
| `queryOrderDetailInfo` | 查订单状态与取餐码 |
| `cancelOrder` | 取消订单 |

## 四、做不到什么（提前说清，别当它全能）

- ❌ 没有销量排行接口
- ❌ 不能选券 / 换券 / 指定某张特定优惠券，价格由服务端自动计算
- ❌ 没有核销码接口，核销只能在品牌 App「我的订单」里出示完成
- ⚠️ 最终支付确认是本人动作，扫码 / 输密码必须真人来做，AI 不代付

## 五、示例

```
用自然语言就行了：

「找一下附近的瑞幸门店」
「帮我来一杯冰美式」
「来两杯热拿铁」
「使用优惠券，下一杯生椰拿铁」
「帮我看一下最近的订单」
```

## 六、安全声明

Token 是你个人的门票，等同账号点单 / 查单权限。请勿提交进仓库、勿截图外发；一旦泄露，尽快到官方渠道作废重发。
