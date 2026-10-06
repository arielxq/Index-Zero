# UART JSON、緩衝區與請求／回應

## 資料流

```text
JSON 字串 → UART bytes → 接收緩衝區 → 依換行切割 → json.loads → 欄位驗證
```

每筆 JSON 使用換行作為訊息邊界，例如 `{"temperature":25.0,"humidity":60.0}\n`。接收端必須允許半包與黏包，不能假設一次 `read()` 就是一筆完整資料。

## 請求／回應

```text
Python request → ESP32 parser → 硬體動作 → response JSON → Python 狀態更新
```

延伸閱讀：[03｜UART](../main/03-uart.md)、[pyserial 基礎](../general/serial-basics.md)。
