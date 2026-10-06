# 03｜UART：讓 Python 與 ESP32 雙向通訊

## 本頁資料流

```text
ESP32 DHT11 → UART bytes → pyserial → decode → Python 欄位
Python 命令 → UART → ESP32 parser → LED／顯示器 → 回應
```

## 初始協定

先使用「一行一筆資料」的規則，每筆資料以換行結束。這讓接收端能用緩衝區等待完整訊息，後續再升級為 JSON。

```cpp
Serial.printf("temperature=%.1f,humidity=%.1f\n", temperature, humidity);
```

```python
import serial

with serial.Serial("/dev/cu.usbmodemXXXX", 115200, timeout=1) as port:
    line = port.readline().decode("utf-8", errors="replace").strip()
    print(line)
```

Windows 使用 `COM3` 類似名稱；實際埠號必須依作業系統列出的裝置判斷。

## 任務

1. 以 115200 baud rate 開啟序列埠。
2. 讀取一行並保留原始輸出。
3. 拆出溫度與濕度欄位。
4. 加入逾時與斷線錯誤處理。

## 相關頁面

- [UART JSON、緩衝區與請求／回應](../extensions/uart-json.md)
- [pyserial 連線、讀寫與逾時](../general/serial-basics.md)

[下一步：04｜CSV 與趨勢圖](04-csv-chart.md)
