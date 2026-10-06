# 選做實作：ngrok 設定本機 port

## 資料流

```text
FastAPI localhost:port → ngrok tunnel → 公開 HTTPS endpoint → App／Webhook
```

先在本機確認 API 正常，再啟動 tunnel；外部測試失敗時分開檢查本機服務與 tunnel。
