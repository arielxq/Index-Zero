# 選做專題：進階實務模擬

## 資料流

```text
RC522／感測器／按鈕 → ESP32 → MQTT／HTTP → Python Gateway → App → 控制回傳
```

這條路線需要 Wi-Fi、網路服務與額外硬體。它不是主線完成條件，建議完成主線 01～08 後再開始。

## 專題目標

以門控模擬為例，整合：

- MQTT 發布／訂閱
- SPI 與多裝置
- RC522 RFID
- FastAPI Gateway
- ngrok 公開通道
- Thunkable 或 Blynk App
- BLE 近距離設定

## 建議順序

```text
MQTT → SPI／RC522 → FastAPI → ngrok → App → BLE
```

前往 [前導技術概要](overview.md)。
