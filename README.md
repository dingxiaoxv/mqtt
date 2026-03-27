# MQTT 系统性学习

基于 [EMQX MQTT 教程](https://www.emqx.com/zh/mqtt-guide)，14天密集型学习计划。

## 进度总览

| 阶段 | 内容 | 天数 | 状态 |
|------|------|------|------|
| [01-basics](01-basics/) | 入门基础 | Day 1-3 | 未开始 |
| [02-advanced](02-advanced/) | 进阶指南 | Day 4-7 | 未开始 |
| [03-broker](03-broker/) | Broker 搭建 | Day 8-9 | 未开始 |
| [04-cpp-practice](04-cpp-practice/) | C++ 编程实战 | Day 10-12 | 未开始 |
| 综合项目 | IoT 设备监控系统 | Day 13-14 | 未开始 |

## 教程文章索引

### 入门基础
1. [MQTT 协议入门：基础知识和快速教程](https://www.emqx.com/zh/blog/the-easiest-guide-to-getting-started-with-mqtt)
2. [MQTT 发布/订阅模式介绍](https://www.emqx.com/zh/blog/mqtt-5-introduction-to-publish-subscribe-model)
3. [创建 MQTT 连接时如何设置参数](https://www.emqx.com/zh/blog/how-to-set-parameters-when-establishing-an-mqtt-connection)
4. [通过案例理解 MQTT 主题与通配符](https://www.emqx.com/zh/blog/advanced-features-of-mqtt-topics)
5. [MQTT 会话详解](https://www.emqx.com/zh/blog/mqtt5-new-feature-clean-start-and-session-expiry-interval)
6. [MQTT QoS 0, 1, 2 介绍](https://www.emqx.com/zh/blog/introduction-to-mqtt-qos)

### 进阶指南
1. [保留消息](https://www.emqx.com/zh/blog/mqtt5-features-retain-message)
2. [遗嘱消息](https://www.emqx.com/zh/blog/use-of-mqtt-will-message)
3. [请求/响应](https://www.emqx.com/zh/blog/mqtt5-request-response)
4. [用户属性](https://www.emqx.com/zh/blog/mqtt5-user-properties)
5. [主题别名](https://www.emqx.com/zh/blog/mqtt5-topic-alias)
6. [载荷格式指示与内容类型](https://www.emqx.com/zh/blog/mqtt5-new-features-payload-format-indicator-and-content-type)
7. [共享订阅](https://www.emqx.com/zh/blog/introduction-to-mqtt5-protocol-shared-subscription)
8. [订阅选项](https://www.emqx.com/zh/blog/an-introduction-to-subscription-options-in-mqtt)
9. [订阅标识符](https://www.emqx.com/zh/blog/subscription-identifier-and-subscription-options)
10. [保持连接](https://www.emqx.com/zh/blog/mqtt-keep-alive)
11. [消息过期间隔](https://www.emqx.com/zh/blog/mqtt-message-expiry-interval)
12. [最大报文大小](https://www.emqx.com/zh/blog/best-practices-of-maximum-packet-size-in-mqtt)
13. [原因码及速查表](https://www.emqx.com/zh/blog/mqtt5-new-features-reason-code-and-ack)
14. [增强认证](https://www.emqx.com/zh/blog/leveraging-enhanced-authentication-for-mqtt-security)
15. [控制报文](https://www.emqx.com/zh/blog/introduction-to-mqtt-control-packets)

## 环境搭建

```bash
# Mosquitto broker + 客户端工具
sudo apt install mosquitto mosquitto-clients

# Paho MQTT C 库
git clone https://github.com/eclipse/paho.mqtt.c.git
cd paho.mqtt.c && cmake -Bbuild -H. -DPAHO_WITH_SSL=ON
cmake --build build && sudo cmake --build build --target install

# Paho MQTT C++ 库
git clone https://github.com/eclipse/paho.mqtt.cpp.git
cd paho.mqtt.cpp && cmake -Bbuild -H. -DPAHO_WITH_SSL=ON
cmake --build build && sudo cmake --build build --target install

# 抓包工具
sudo apt install wireshark tcpdump
```
