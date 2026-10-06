# PubSubClient：MQTT 函式庫介紹

## 資料流

```text
ESP32 → Wi-Fi → MQTT Client → connect → Broker → publish／subscribe
```

韌體要定期呼叫 `client.loop()`，並處理斷線重連與訊息回呼；密碼與憑證不要硬編碼進公開 repository。
