# Gradio 事件、狀態與原型邊界

## 資料流

```text
使用者操作 → event handler → 狀態／服務 → 元件更新 → 瀏覽器
```

Gradio 適合快速驗證；當需要權限、多人併發、背景工作或公開 API 時，應把服務邏輯移到 FastAPI 或獨立後端。
