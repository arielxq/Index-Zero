# ngrok：暫時公開通道的概念

## 資料流

```text
外部使用者 → HTTPS 公開網址 → ngrok tunnel → 本機 FastAPI port
```

隧道適合測試與展示，不等同於完整生產環境安全設計；公開前要處理驗證、秘密與資料暴露範圍。
