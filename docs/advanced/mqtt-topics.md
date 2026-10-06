# PubSubClient：兩個 Topic 的控制與回傳

## 資料流

```text
App／Python → device/control → ESP32 → 執行 → device/status → App／Python
```

控制與狀態使用不同 Topic，能避免把命令誤當成回報，也方便追蹤請求與結果。
