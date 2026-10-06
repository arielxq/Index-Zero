# Thunkable：App 與 Web API 的概念

## 資料流

```text
Thunkable App → HTTP request → FastAPI／資料 API → JSON → App 元件更新
```

App 負責呈現與操作，Gateway 負責驗證、協定轉換與硬體服務。
