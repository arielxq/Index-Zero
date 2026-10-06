# 延伸選讀：Blynk App 與 Gateway 的產品架構取捨

## 資料流

```text
Blynk App → Blynk Cloud → ESP32／Gateway
自建 App → 自建 API Gateway → MQTT／資料庫／ESP32
```

Blynk 讓原型快速成形；自建 Gateway 提供更多資料模型、權限與部署控制，但維護責任也更高。
