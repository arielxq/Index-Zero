# MQTT 基礎：發布、訂閱與 Broker

## 資料流

```text
Publisher → publish topic → Broker → subscribe → Subscriber
```

ESP32 可以發布感測資料，也可以訂閱控制命令；Broker 負責路由，不直接理解你的硬體語意。
