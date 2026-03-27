# MQTT 系统性学习计划

基于 [EMQX MQTT 教程](https://www.emqx.com/zh/mqtt-guide)，14天密集型学习。

---

## 阶段一: 入门基础 (Day 1-3)

### Day 1 — 协议入门 + 发布订阅模型
- [ ] 阅读: [MQTT 协议入门：基础知识和快速教程](https://www.emqx.com/zh/blog/the-easiest-guide-to-getting-started-with-mqtt)
- [ ] 阅读: [MQTT 发布/订阅模式介绍](https://www.emqx.com/zh/blog/mqtt-5-introduction-to-publish-subscribe-model)
- [ ] 实操: 安装 Mosquitto，用命令行工具完成首次 pub/sub
- [ ] 笔记: 记录核心概念 (Broker/Publisher/Subscriber、解耦特性)
- 产出 → `01-basics/notes.md`、`01-basics/exercises/day1_pubsub.sh`

### Day 2 — 连接参数 + 主题与通配符
- [ ] 阅读: [创建 MQTT 连接时如何设置参数](https://www.emqx.com/zh/blog/how-to-set-parameters-when-establishing-an-mqtt-connection)
- [ ] 阅读: [通过案例理解 MQTT 主题与通配符](https://www.emqx.com/zh/blog/advanced-features-of-mqtt-topics)
- [ ] 实操: 测试各种通配符匹配 (`+`、`#`)，验证边界情况
- [ ] 练习: 为一个智能工厂场景设计 Topic 层级结构
- 产出 → `01-basics/exercises/day2_topics.md`

### Day 3 — 会话 + QoS
- [ ] 阅读: [MQTT 会话详解](https://www.emqx.com/zh/blog/mqtt5-new-feature-clean-start-and-session-expiry-interval)
- [ ] 阅读: [MQTT QoS 0, 1, 2 介绍](https://www.emqx.com/zh/blog/introduction-to-mqtt-qos)
- [ ] 实操: 用 `mosquitto_pub -q` 分别测试 QoS 0/1/2，观察行为差异
- [ ] 实操: 验证 Clean Session 与持久会话的离线消息行为
- [ ] 练习: 画出 QoS 2 四步握手流程图
- 产出 → `01-basics/exercises/day3_qos_test.sh`

---

## 阶段二: 进阶指南 (Day 4-7)

### Day 4 — 保留消息 + 遗嘱消息 + Keep Alive
- [ ] 阅读: [保留消息](https://www.emqx.com/zh/blog/mqtt5-features-retain-message)
- [ ] 阅读: [遗嘱消息](https://www.emqx.com/zh/blog/use-of-mqtt-will-message)
- [ ] 阅读: [保持连接](https://www.emqx.com/zh/blog/mqtt-keep-alive)
- [ ] 实操: 发送 Retained Message，新订阅者验证立即收到
- [ ] 实操: 设置 LWT，强制断开客户端观察遗嘱发布
- 产出 → `02-advanced/exercises/day4_retained_lwt.sh`

### Day 5 — MQTT 5.0 核心新特性 (上)
- [ ] 阅读: [用户属性](https://www.emqx.com/zh/blog/mqtt5-user-properties)
- [ ] 阅读: [主题别名](https://www.emqx.com/zh/blog/mqtt5-topic-alias)
- [ ] 阅读: [载荷格式指示与内容类型](https://www.emqx.com/zh/blog/mqtt5-new-features-payload-format-indicator-and-content-type)
- [ ] 阅读: [请求/响应模式](https://www.emqx.com/zh/blog/mqtt5-request-response)
- [ ] 笔记: 对比 MQTT 3.1.1 和 5.0 的关键差异
- 产出 → `02-advanced/notes.md`

### Day 6 — MQTT 5.0 核心新特性 (下)
- [ ] 阅读: [共享订阅](https://www.emqx.com/zh/blog/introduction-to-mqtt5-protocol-shared-subscription)
- [ ] 阅读: [订阅选项](https://www.emqx.com/zh/blog/an-introduction-to-subscription-options-in-mqtt)
- [ ] 阅读: [订阅标识符](https://www.emqx.com/zh/blog/subscription-identifier-and-subscription-options)
- [ ] 阅读: [消息过期间隔](https://www.emqx.com/zh/blog/mqtt-message-expiry-interval)
- [ ] 阅读: [最大报文大小](https://www.emqx.com/zh/blog/best-practices-of-maximum-packet-size-in-mqtt)
- 产出 → `02-advanced/notes.md` (补充)

### Day 7 — 控制报文 + 原因码 + 增强认证
- [ ] 阅读: [控制报文详解](https://www.emqx.com/zh/blog/introduction-to-mqtt-control-packets)
- [ ] 阅读: [原因码及速查表](https://www.emqx.com/zh/blog/mqtt5-new-features-reason-code-and-ack)
- [ ] 阅读: [增强认证](https://www.emqx.com/zh/blog/leveraging-enhanced-authentication-for-mqtt-security)
- [ ] 实操: 用 Wireshark 抓取 MQTT 报文，对照文章手动解析
- [ ] 练习: 解析一个完整的 CONNECT 报文 (逐字节标注)
- 产出 → `02-advanced/exercises/day7_packet_analysis.md`

---

## 阶段三: Broker 搭建与实战 (Day 8-9)

### Day 8 — Mosquitto 深入配置
- [ ] Mosquitto 配置文件详解 (listener, protocol, persistence)
- [ ] 用户名/密码认证 (`password_file`)
- [ ] ACL 权限控制 (`acl_file`)
- [ ] TLS/SSL 配置 (生成自签名证书 + 配置加密通信)
- [ ] `$SYS` 系统主题监控
- 产出 → `03-broker/configs/`

### Day 9 — Docker 部署 + EMQX 体验
- [ ] Docker 部署 Mosquitto
- [ ] Docker 部署 EMQX (体验 Dashboard 和规则引擎)
- [ ] Broker 桥接配置 (Mosquitto ↔ Mosquitto)
- [ ] 对比 Mosquitto vs EMQX 的功能差异
- 产出 → `03-broker/docker/docker-compose.yml`

---

## 阶段四: C++ 编程实战 (Day 10-12)

### Day 10 — 环境搭建 + 基础客户端
- [ ] 编译安装 Paho MQTT C/C++ 库
- [ ] CMake 项目配置
- [ ] 实现同步 Publisher: 温度传感器模拟器
- [ ] 实现同步 Subscriber: 数据接收并打印
- [ ] 测试 QoS 0/1/2 下的发布订阅
- 产出 → `04-cpp-practice/basic/`

### Day 11 — 异步客户端 + 高级功能
- [ ] `mqtt::async_client` 使用
- [ ] 回调 (callback) 与 Token 机制
- [ ] 自动重连与消息持久化
- [ ] SSL/TLS 连接配置
- [ ] LWT 和 Retained Message 在代码中的使用
- 产出 → `04-cpp-practice/async/`

### Day 12 — 健壮客户端封装
- [ ] 封装一个可复用的 MQTT 客户端类
- [ ] 连接状态管理 (断线重连、指数退避)
- [ ] 消息序列化 (JSON)
- [ ] 多线程安全考虑
- [ ] 单元测试
- 产出 → `04-cpp-practice/` (重构整理)

---

## 阶段五: 综合项目 (Day 13-14)

**项目: IoT 设备监控系统**

### Day 13 — 设计与核心实现
- [ ] 系统架构设计 (Topic 结构、QoS 策略、安全方案)
- [ ] 设备模拟器: 多种传感器 (温湿度、开关) 的 Publisher
- [ ] 控制中心: 异步 Subscriber + 命令下发
- [ ] Retained Message 管理设备状态
- [ ] LWT 实现设备上下线检测

### Day 14 — 完善与总结
- [ ] 告警逻辑 (阈值触发)
- [ ] TLS 安全通信集成
- [ ] 整体测试与 Bug 修复
- [ ] 学习总结文档
- 产出 → `04-cpp-practice/project/`

---

## 每阶段验证标准

| 阶段 | 通过标准 |
|------|---------|
| 入门基础 | 能独立解释 QoS 三级别差异，能设计合理的 Topic 结构 |
| 进阶指南 | 能说出 MQTT 5.0 至少5个新特性及其用途，能手动解析报文 |
| Broker实战 | 能配置带 TLS+认证 的 Mosquitto，能搭建桥接 |
| C++编程 | 异步客户端能稳定运行，支持断线重连 |
| 综合项目 | 完整的设备监控系统可演示运行 |
