# 05｜I2C：使用 LCD1602A 顯示 DHT11 資料

## 本頁資料流

```text
DHT11 GPIO 4 → ESP32 → I2C SDA/SCL → LCD1602A → 兩行文字
```

## 指定接線

| LCD1602A I2C | ESP32 | 說明 |
| --- | --- | --- |
| GND | GND | 共地 |
| VCC | 3V3 | 本主線核心接法 |
| SDA | GPIO 21 | I2C 資料線 |
| SCL | GPIO 22 | I2C 時脈線 |

DHT11 沿用已驗證的 `GPIO 4` 接法。LCD 的位址不是 GPIO，必須先用 I2C scanner 查出，常見值為 `0x27` 或 `0x3F`。

## 分段任務

1. **掃描位址**：`Wire.begin(21, 22)`，確認裝置回應。
2. **固定文字**：先使用 `lcd.init()` 與 `lcd.backlight()`。
3. **感測顯示**：每約 2 秒讀取 DHT11，更新 `T` 與 `H`。

!!! warning "電壓安全"
    不要把 5V LCD 的 SDA、SCL 直接接到 ESP32。若模組在 3.3V 無法正常工作，應使用雙向 I2C 電平轉換器；不可用一般電阻分壓取代。

## 成功條件

- 找到實際 I2C 位址。
- LCD 能顯示兩行固定文字。
- LCD 能顯示 DHT11 溫度與濕度。

[下一步：06｜74HC595 與裸 8×8 點陣](06-matrix.md)
