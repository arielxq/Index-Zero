# BLE：手機與 ESP32 的近距離設定概念

## 資料流

```text
手機掃描 → ESP32 Advertiser → 連線 → GATT Service → Characteristic read／write／notify
```

BLE 適合近距離初始設定與固定資料交換；大量資料與遠端控制應評估 Wi-Fi、MQTT 或 API。
