# SPI 通訊與多裝置

## 資料流

```text
ESP32 SPI Master → SCK／MOSI／MISO → 個別 CS → RC522／其他裝置
```

共用時脈與資料線，但每個裝置要有獨立 Chip Select；未選取的裝置不能同時驅動 MISO。
