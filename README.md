# GohnStudio
- GohnStudio WorkSpace
```java
title 支付流程

游戏客户端->+SDK客户端: 调用充值接口[充值信息]
SDK客户端->+SDK服务端: 发送下单请求[充值信息]
SDK服务端->-SDK客户端: 服务处理下单请求[订单号]
SDK客户端->-SDK客户端: 调用支付
SDK客户端->+SDK服务端: 返回支付结果
SDK服务端->+游戏服务器: 返回充值结果
游戏服务器->-SDK服务端: 返回接收状态

游戏客户端->+游戏服务器: 请求更新

游戏服务器->+游戏客户端: 处理更新
```
```java
title 登录流程

游戏客户端->+SDK客户端: 调用充值接口[appid,cpid/uid,pwd]
SDK客户端->+SDK服务端: 服务处理登陆请求[sid]
SDK客户端->+游戏客户端: 回调机制[sid]
游戏客户端->+游戏服务器: 发送请求[sid]

游戏服务器->-SDK服务端: 发送验证请求[sid,appid,cpid]
note right of SDK服务端: 处理用户token验证
SDK服务端->+游戏服务器: 服务处理验证请求[uid/userinfo]

游戏服务器->-游戏客户端: 返回登陆结果[uid/userinfo]
```
