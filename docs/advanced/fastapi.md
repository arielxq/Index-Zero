# FastAPI：Gateway API 的基本概念

## 資料流

```text
App／瀏覽器 → HTTP request → FastAPI → 驗證 → MQTT／UART／資料庫 → JSON response
```

Gateway 將 App 與硬體協定隔離，API 不應讓前端直接管理序列埠細節。
